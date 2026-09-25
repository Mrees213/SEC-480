## 1. What I set up

For Module 1, I created my private `sec-480` GitHub repository, added my name to the README, invited `derp-cc` as a collaborator, and created the required `hello-world.md` file.

I also connected Claude to my GitHub repository.

To test whether the connection actually worked, I asked Claude to read the README and identify my name. Claude accessed the README and correctly reported that it contained the heading `Morgan Rees, SEC-480`. It then correctly identified my first name as Morgan and my last name as Rees.

This confirmed that Claude was actually able to read information from my repository instead of simply showing that GitHub was connected.

## 2. What took more than one attempt

The Claude and GitHub integration took more than one attempt.

At first, when I looked through Claude's connector options, I was seeing GitLab instead of GitHub. This confused me because the Module 1 instructions specifically referred to the GitHub connector.

I initially thought that SEC 480 might use a separate Claude account or workspace. I also discovered that the Claude account I was using was a free account, which made the available connector options different from what I expected.

After working through the account and connector problem, I was eventually able to connect Claude to GitHub and successfully test access to my repository.

## 3. What surprised me

One thing that surprised me was that seeing a connector listed as connected is not enough to prove that it actually works.

Before this lab, I probably would have assumed that if Claude said GitHub was connected, then the integration was working correctly. Instead, the lab required me to prove it by asking Claude for information that it could only know by reading my repository.

When Claude correctly read `Morgan Rees, SEC-480` from my README, that gave me actual evidence that the integration was working. This showed me why it is important to verify what a system can actually do instead of trusting its status screen.
