Security Investigation Interview: Questions and Answers
Sep 27, 2026 · @Morgan
Overview
Claude interviewed me about how I investigate a suspected account compromise, before seeing any log. Claude asked the questions; the answers are mine, kept exactly as I typed them.
The interview covered all ten required topics: the actual question, evidence, facts, assumptions, timestamps, suspicious logins, correlation vs. proof, incomplete evidence, verifying AI claims, and communicating uncertainty. Each question below is labeled with the topic it addresses.
Interview
Q1. The actual question
Q: Imagine someone hands you a security problem, like "we think an account might have been compromised, can you look into it?" Before you open a single log file or tool, what's the very first thing you do or think about?
A: how was comromised and if it was what attack would it be
Q2. The actual question
Q: You said "if it was." "How was it compromised?" assumes it already happened, while "was it compromised?" is still an open question. If you had to pick one of those as the question you're actually trying to answer first, which would it be, and why?
A: I owuld ay if it awas comprised
Q3. The actual question
Q: Why do you think it matters to settle that first? What could go wrong if you skipped it and jumped straight to figuring out which attack it was?
A: becuase if it wasn't comrpomsied then eithe rthe attack failed or ther was no attack atall
Q4. What evidence do I have?
Q: Say you're trying to figure out whether the account was compromised. What kinds of evidence would you want to get your hands on, and where would you expect to find them?
A: I would look at a log ot figure out like how failed attaemtps there, was that attempt susefful and what was gioign stuff liek that
Q5. What makes a login suspicious?
Q: When you look at one login attempt in a log, what specific details would you check to decide whether it looks normal or suspicious?
A: if tehres like a bunch of failed attempts along with signs sshd was acsksed and used ot atemtpt tolog in
Q6. What makes a login suspicious?
Q: A bunch of failed logins could be an attacker brute-forcing the password, but it could also be the real user who forgot their password, or a script with an old password saved in it. What other details in those log entries would help you tell the difference between an attacker and a legit user having a bad day?
A: I would say it saying sshd would b e a big hint
Q7. What makes a login suspicious?
Q: On a lot of Linux servers, SSH is the normal way people log in, so "sshd" tells you which door someone used, but not who was knocking. What about where the attempt came from, and when it happened? How might those help you decide if it's the real user or someone else?
A: I think its says where it comee sfrom i the log
Q8. What makes a login suspicious?
Q: If you see an IP address in the log, how would you decide whether it's one you'd expect to see for this user, or one that should make you suspicious?
A: usally i would have already had list of ip addreses for the domain already set so
Q9. Facts vs. assumptions
Q: Say you find a successful login from an IP that's not on your list. Is that enough to say the account was compromised? What else could explain it?
A: it could enoug it could not be that requesires actualyl ivnesiraitng
Q10. Facts vs. assumptions
Q: The fact is "a successful login came from IP X, which isn't on our list." The assumption would be "so an attacker got in." So what would "actually investigating" look like for you? What would you check next to move from "this looks weird" toward "yes, this was a compromise" or "no, it's fine"?
A: inspecting hte logs nad looking at the activites they were doing
Q11. What makes a login suspicious?
Q: What kinds of activities after a login would make you think "okay, this is probably an attacker" rather than the normal user?
A: I would flag attempts to change account credentials, because that could mean someone is trying to maintain access or take control of an account. I would also look closely at unexpected successful logins, especially if they come from an unfamiliar IP address, use a different authentication method than normal, or happen around suspicious failed login attempts.
Q12. What do I do when timestamps differ?
Q: Say you're lining up events from two different logs, like the SSH log and a separate account-change log, and the timestamps don't quite match up. One says the login was at 2:14 and the credential change was at 2:09, which would mean the change happened before the login. How would you handle that?
A: I would treat that as a red flag and stop before assuming the order of events is correct. I would first check whether the two logs are using the same timezone, whether either system has clock drift, and whether the timestamps are recorded in the same format.
Then I would inspect the account involved to see what actually changed, whether the credential change was expected, who or what initiated it, and whether there were other logins or account events around the same time.
I would not conclude that the credential change happened before the login until I had verified the timestamps and the account activity. I would treat the timeline as uncertain until those differences were explained.
Q13. Correlation vs. proof
Q: Say you find a string of failed logins from one IP, and a few minutes later a successful login from that same IP. It really looks like a brute-force attack that worked. What would it take for you to go from "these events are connected" to "this proves the account was compromised"?
A: The failed logins followed by a successful login from the same IP would make me strongly suspect the events are connected, but I would not call that proof of compromise by itself.
To move from suspicion to confirmed compromise, I would want to see what happened after the successful login. I would look for things like commands being executed, credential or SSH key changes, new accounts, privilege escalation, unusual file changes, persistence, or other activity that the legitimate user did not perform.
I would also want to verify whether the successful login was expected and whether that IP actually belonged to the legitimate user. If the login was followed by unauthorized activity, that would be much stronger evidence that the account was compromised.
Q14. What if the evidence is incomplete?
Q: Say you go looking for that post-login activity, and there's a gap. The logs for the hour after the login are missing, or the system just doesn't record commands. What do you do when the evidence you need isn't there?
A: If the logs I need are missing, I would treat that as a serious limitation and immediately look for other sources of evidence instead of assuming what happened.
I would check things like Windows Event Viewer or other system logs, authentication logs, account-change events, privilege changes, file changes, endpoint security logs, network logs, and anything else that could show what happened after the login.
If the system does not record commands, I would try to reconstruct the activity from the evidence that does exist.
If I still could not determine what happened, I would say that the evidence is insufficient to confirm compromise rather than guessing. I would also document exactly what evidence is missing and what additional logs or records would be needed to answer the question.
Q15. How do I verify an AI-generated claim?
Q: Say you paste a log into an AI tool and it tells you, "This shows a successful brute-force attack from IP X at 2:14, followed by the attacker changing the password." How would you check whether that's actually true before you trust it?
A: I would not trust that conclusion immediately. I would go back to the raw logs myself and verify each part of what the AI claimed.
First, I would check whether there really was a successful login at that time and whether it actually came from the same IP as the failed attempts. Then I would check what authentication method was used and whether the account involved matches the failed login attempts.
After that, I would look for actual evidence of the password change, such as an account-change event or another log that records credential modifications. If I could not find that evidence, I would not repeat the AI's claim that the attacker changed the password.
I would treat the AI's answer as a hypothesis until I had confirmed the events directly from the logs.
Q16. How do I communicate uncertainty?
Q: Once you've done all this, you have to report back to someone, like a manager or a client. How would you communicate what you found when some of it is confirmed, some of it is likely, and some of it you just don't know?
A: I would separate the report by certainty instead of presenting everything as equally proven.
I would clearly state what is confirmed by the evidence, what I think is likely based on the evidence, and what is still unknown. I would probably use wording like high confidence, moderate confidence, or low confidence, but I would also explain why I have that confidence level instead of just giving it a label.
For example, I might say that a successful login from a specific IP is confirmed by the log, that compromise is likely if that login followed repeated failed attempts and other suspicious activity, and that actions taken after the login are unknown if the relevant logs are missing.
I would also explain what additional evidence would be needed to raise or lower my confidence. That way the manager or client can tell the difference between what I know, what I suspect, and what I cannot determine.
Summary of my process
1. Start by asking whether a compromise happened at all, before asking how.
2. Use logs as the main evidence and compare against a known baseline, like the list of expected IPs.
3. Treat unfamiliar IPs or failed-then-successful logins as leads, not proof.
4. Check timezones, clock drift, and formats before trusting a timeline across logs.
5. Confirm compromise through what happened after the login, like credential changes or unauthorized activity.
6. When logs are missing, look for other sources; if the gap can't be filled, say the evidence is insufficient and document what's missing.
7. Break AI claims into pieces and verify each one against the raw logs.
8. Report findings as confirmed, likely, or unknown, with the reason for each confidence level.
