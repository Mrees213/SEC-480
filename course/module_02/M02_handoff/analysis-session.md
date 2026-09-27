I went through the ticket using your ten-step process. The short answer is that **there's no evidence the brute force got in, but the log can't show the host is clean.** One successful login in the log hasn't been verified, and 20 lines can't show what happened afterward.

## Step 1: The actual question

Priya is asking whether anybody got in. She is not asking what the attack was. So the useful answer is about whether any access happened, and whether that access was legitimate.

## Steps 2–5: What the log shows once timestamps are normalized

The log has 19 failed password attempts from 203.0.113.44, between 03:14:07 and 03:14:50 EDT (-04:00). Every one of them says **"invalid user."** That means sshd rejected the username before the password mattered. The names tried were admin, root, oracle, postgres, test, ubuntu, git and jenkins. This looks like an automated scanner guessing common account names. None of these attempts could have succeeded, whatever password was used.

There is also one successful login: `Accepted publickey for deploy from 198.51.100.9` at **07:14:31+00:00**. This line is in UTC, while every other line is in -04:00. Converted, it is **03:14:31 EDT**. That puts it in the middle of the burst, between the 03:14:29 and 03:14:33 failures. The handoff note says "Timestamps are in local time. I think." That is wrong for this line, and without converting it you would misplace it by four hours.

## Steps 6–7: Correlation vs. proof

The successful login happened during the attack, but nothing else connects it to the attack:

| | Brute force | Successful login |
|---|---|---|
| Source IP | 203.0.113.44 | 198.51.100.9 |
| Account | Nonexistent names | `deploy` (a real account) |
| Method | Password | Public key |

The attacker never tried "deploy" and never tried a key. The two events happened at the same time, and that is their only link. The handoff advice to "skim for the successful login and start from there" would lead straight into connecting them anyway.

That doesn't make the deploy login safe. It just means it has to be verified separately. Nothing in these 20 lines shows whether it was expected, or what happened after it.

## Integrity problems with the log itself

Before anything relies on this file, it's worth noting that it doesn't look like raw, unedited sshd output:

- **The PIDs go out of order.** The accepted login has PID 20655, but the failures that come after it have lower PIDs (20519–20546). PIDs normally increase, so a later process shouldn't have a lower number. The accepted line may have been merged in from another source, or the file may have been assembled from several places.
- **The timezone format is mixed.** One line is in UTC and the rest are in -04:00, which points the same way.
- **"invalid user root" is unusual.** On a standard Linux host, root always exists, so sshd would normally log "Failed password for root" instead. Either this host is non-standard or the line has been changed.
- **The key fingerprint is cut short.** `SHA256:8f2c9a1e4b7d` is 12 characters, but a real SHA256 fingerprint is 43. At this length it can't be matched against deploy's `authorized_keys`.
- **Both IPs are in reserved documentation ranges** (RFC 5737). They may have been anonymized. If so, the real addresses are needed before anyone can check them against a baseline or reputation data.

None of these mean the host was compromised. They do lower how much weight this file can carry.

## Step 8: What's missing

The alert was open from 03:14 to 03:20, but the log only covers 43 seconds (03:14:07–03:14:50). We can't see whether the attempts continued, changed usernames, or succeeded after 03:14:50. We also can't see anything the deploy session did.

## Step 10: Findings by certainty

**Confirmed:** A brute-force attempt came from 203.0.113.44, and every attempt in the log failed against nonexistent usernames. A public-key login for `deploy` succeeded from 198.51.100.9 at 03:14:31 EDT.

**Likely:**
- *High confidence:* The brute force did not gain access during the 43 seconds shown. Invalid-user attempts can't succeed.
- *Moderate confidence:* The deploy login is unrelated to the attack. It shares no IP, account or method with it. This is only moderate because it hasn't been verified and the file has integrity problems.

**Unknown:**
- Whether the deploy login was expected.
- What happened after it.
- What happened between 03:14:50 and 03:20.
- Whether this file matches the original log.

## Draft reply to Priya

> **Was the host compromised?** Not by the attack that set off the alert, as far as the log shows. Every attempt in it failed, and they were all against usernames that don't exist on the host, so they couldn't have worked.
>
> I can't yet say the host is clean, for two reasons. First, the log shows one successful login during the attack: the `deploy` account, from a different address, using a key rather than a password. Nothing links it to the attacker, but nobody has confirmed it was expected. Second, the log covers only 43 seconds of a 6-minute alert.
>
> To close this out today I need three things:
> 1. The owner of `deploy` to confirm whether a key login from 198.51.100.9 at 03:14 EDT on 28 Aug was expected, for example a scheduled deploy job.
> 2. A check of `deploy`'s authorized keys for anything unfamiliar.
> 3. Any other copy of the logs for 03:14–03:20 (the monitoring or SIEM system, the journal, or login records).
>
> If the deploy login checks out and the remaining minutes show no success, I'd close this as a failed attack. If it doesn't check out, this becomes an incident.

One thing this case suggests adding to your process: **check the log's integrity before analyzing it.** That means looking at PID order, consistent formatting, and whether it covers the full window you're asking about. Your step 5 covers timestamps, but here the file itself was the weakest piece of evidence.
