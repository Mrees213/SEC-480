# Finding — Ticket SD-4471

## Question

Was `web01` compromised?

## Finding

The available evidence does not show that the failed SSH activity from `203.0.113.44` successfully compromised `web01`.

The supplied authentication log contains repeated failed password attempts against invalid usernames from `203.0.113.44`. None of those entries shows a successful authentication from that source.

The log also contains one successful public-key authentication for the `deploy` account from `198.51.100.9`. After normalizing the timestamp, that login occurred during the same general time period as the failed attempts. However, the successful login differs from the failed activity in source IP address, account, and authentication method.

Because of those differences, the available evidence does not establish that the successful `deploy` login was the result of the failed-password activity.

## Confirmed

The following can be confirmed from the supplied log:

- Multiple failed SSH authentication attempts occurred from `203.0.113.44`.
- The failed attempts targeted several usernames including `admin`, `root`, `oracle`, `postgres`, `test`, `ubuntu`, `git`, and `jenkins`.
- The supplied failed-login entries do not show a successful authentication from `203.0.113.44`.
- A successful public-key authentication occurred for the `deploy` account from `198.51.100.9`.
- The successful login occurred at `07:14:31+00:00`, which corresponds to approximately `03:14:31-04:00`.
- The successful `deploy` login therefore occurred during the same general period as the failed authentication attempts.

## Likely

The failed authentication activity appears consistent with automated attempts against commonly used account names.

The successful `deploy` login is likely separate from the failed-password activity because it:

- came from a different source IP address,
- used a different account,
- and used public-key authentication instead of password authentication.

However, the supplied evidence is not enough to confirm that the `deploy` login was legitimate.

## Unknown

The available evidence does not establish:

- whether the `deploy` login was expected,
- whether `198.51.100.9` was an approved source,
- what activity occurred after the successful login,
- whether additional successful logins occurred after the supplied log ends,
- or whether anything occurred between approximately 03:14:50 and the end of the alert period at 03:20.

## Limitations

The ticket states that the monitoring alert lasted from approximately 03:14 to 03:20, but the supplied authentication log covers only a small portion of that period.

Because the evidence is incomplete, I cannot determine with certainty that the host was not compromised. I can only state that the supplied log does not show the failed-password activity from `203.0.113.44` successfully authenticating.

## Additional Evidence Needed

To reach a stronger conclusion, I would want:

1. Authentication logs covering the full 03:14–03:20 alert period.
2. Confirmation from the owner or administrator of the `deploy` account about whether the public-key login from `198.51.100.9` was expected.
3. Information about approved or known source IP addresses for the `deploy` account.
4. Relevant system, security, endpoint, or network logs showing activity after the successful `deploy` login.
5. Account-change records that could show password, SSH key, privilege, or other credential changes.

## Conclusion

Based on the evidence provided, there is no confirmed compromise resulting from the failed SSH attempts shown in the log.

However, the host cannot be declared clean from these twenty lines alone. The successful `deploy` login needs to be verified separately, and additional evidence is needed to determine what happened during the remainder of the alert window and after the successful authentication.
