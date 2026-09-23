<h3 align="center">SEC 480: Advanced AI Practicum</h3>

# Setup: accounts, repository, and proving the connections work

> **Due Friday 04 September, 9:00 pm.** This material reached your repository later than intended;
> the deadline above already accounts for that. It is in `course/module_01/` in your own
> `sec-480` repository, and it stays there for reference after you have handed the work in.

## What this is

By the end of this you will have a private repository that I can see, a working copy on the
machine you actually use, one file in it that you made with AI and pushed yourself, and proof
that Claude can read what is in that repository.

Parts one and two are step by step. Follow them in a browser, on whatever machine you are
sitting at. They are the foundation everything else rests on and there is nothing to be gained
from improvising them.

From part three onward the instructions stop telling you which buttons to press. The work does
not get easier, it gets harder: you start making decisions instead of following a sequence, and
you are expected to justify them. Where you get stuck at any point, the troubleshooting section
at the end covers what actually goes wrong, and `help.me` gets you a response without leaving
the browser.

## The idea running through the whole thing

There are two different connections being built here, and each one gets proved separately.

**You to GitHub.** Your work leaves your machine and arrives somewhere I can see it.

**Claude to GitHub.** The platform can actually read what is in your repository.

Neither is proved by a settings screen. Authorizing a connection means a service now holds a
token. Validating it means you have watched information move and you know what it looks like
when it works. A green checkmark is a claim the system makes about itself. You will be asked
for evidence, not for a checkmark.

## Do these two first

This lab has a lot of moving parts. Two of them block everything else in the course, so they
come first and the rest follows in order. If you only get two things done, get these two:

1. Your repository exists, it is private, and you have invited me to it. Acceptance is
   automatic, so there is nothing to wait for.
2. Your `hello-world.md` is committed.

Everything after them is still expected. It is a sequence, not a menu.

## Where you will work

Expect that the lab workstation will not let you install anything. That is normal and it is not a
problem, because nothing required here needs an installer.

| Environment | Install rights | Survives a reboot | Use it for |
|---|---|---|---|
| Lab workstation, browser only | No | n/a | Every required checkpoint here |
| A VM you create on the lab workstation | Yes, inside the VM | Yes, on that workstation | The full setup, git included |
| View Portal, `viewportal.champlain.edu` | Yes | **No** | A real git client on campus without building anything |
| Your own machine | Yes | Yes | Your permanent working copy |

Everything mandatory here can be done in a browser. GitHub's web interface creates files,
edits them, and commits, which covers every required checkpoint.

### Side note: no install rights on the workstation

Your lab account cannot install software on the host. That blocks a local git client, and there
are two easy ways around it.

**Create your own VM on the lab workstation.** You can build one even without host install
rights, and inside that VM you are administrator. Install git, install anything,
and browse from in there too. A GUI Linux distribution is the path of least resistance. This is
the better option if you want to work the way you will work all term.

The VM persists on the workstation you built it on, so sit in the same seat each week. If you
end up on a different machine, rebuilding is quick and everything that matters is
already in GitHub. That is the same lesson again, arriving from a different direction.

**Or use View Portal.** Log in with your usual credentials and you get a Windows 11 desktop with
administrative rights. Nothing to build, and you can make real progress immediately. The catch
is that it is not persistent: when it powers down, your installs and local files go with it, and
you will set git up again next time.

That sounds worse than it is, because everything that matters lives in GitHub, so recovering is
a clone rather than a rebuild. Notice that this is itself the lesson. Work that exists on one
machine is work you can lose. Work that has been pushed is not.

**On your own machine, set up a permanent working copy.** That is where pushing and pulling
becomes a habit rather than a demonstration, and where most of your real work this term will
happen.

### Installing git on your own machine

| Your machine | What to do |
|---|---|
| **Windows** | Install Git for Windows, or GitHub Desktop for a graphical client. Both are free and neither needs administrator rights on a personal machine |
| **macOS** | Run `git --version` in Terminal and accept the prompt to install developer tools, or use Homebrew or GitHub Desktop |
| **Linux** | Install through your package manager: `apt install git`, `dnf install git`, or your distribution's equivalent |

## Objectives

1. Confirm access to your institutional Claude account, and note which tier it is.
2. Confirm access to your GitHub account.
3. Create a private repository named `sec-480` and invite the instructor to it.
4. Produce your first artifact with Claude and commit it.
5. Answer the response that comes back.
6. Authorize the Claude to GitHub connection.
7. Prove that connection reads real content, in both directions of freshness.
8. Write up what you did and what went wrong.

---

# Part one: you and GitHub

This part is prescriptive on purpose: everything else in the course sits on top of it, and a
small mistake here is expensive to find later.

## 1. Sign in to both accounts

1. Open `claude.ai` and sign in with your school account.
2. Note which plan you are on. It is shown in your account settings.
3. Open `github.com` and sign in.

**Checkpoint 1.** Both are open in front of you.

## 2. Create the repository

1. On GitHub, click the **+** in the top right, then **New repository**.
2. Repository name: `sec-480`. Lower case, with the hyphen, exactly.
3. Description: leave blank.
4. Select **Private**.
5. Tick **Add a README file**.
6. Click **Create repository**.
7. On the repository page, click `README.md`, then the pencil icon to edit.
8. Replace the contents with one line: your first and last name, then the course. For
   example `Rose Davis, SEC 480`.
9. Click **Commit changes**, then **Commit changes** again in the dialog.

First and last name as they appear on the class roster, not a nickname. If you are unsure which form that is, open the Canvas shell for this course and look at the **People** section: the name listed there is the one to use. The course tooling reads this line to know whose repository it is.

**Checkpoint 2.** The repository page shows `Private` next to its name, and the README shows
your first and last name.

## 3. Invite your instructor

1. On your repository, click **Settings**.
2. In the left sidebar, click **Collaborators**.
3. Click **Add people**.
4. Type the username on the board and select it from the list.
5. Click **Add to this repository**.

The invitation is accepted automatically within a few minutes. You do not need to wait for it
or ask me to confirm.

**Checkpoint 3.** Under Collaborators, the instructor appears as pending, then as a
collaborator once it is accepted.

## 4. Create your hello world

1. Open a conversation in Claude.
2. Ask it to help you write a short markdown file introducing yourself, with these four lines
   in this order:
   - `Name:` your first and last name
   - `Program:` your program
   - `Graduating:` the year you expect to graduate, four digits
   - `Want from this course:` a sentence or two, honest rather than impressive
   - `Something I do well:` one sentence, and it does not have to be technical
3. Copy the result.
4. On GitHub, on your repository page, click **Add file**, then **Create new file**.
5. Name the file `hello-world.md`.
6. Paste what Claude produced.
7. Underneath it, add a heading `## The prompt I used`, and paste the exact text you typed
   into Claude. Copy it as written, including any typos, rather than rewriting it afterwards.
8. Click **Commit changes**, then **Commit changes** again.

**Checkpoint 4.** Open `hello-world.md` from the repository file list and read it. Seeing the
filename is not enough. Read the contents, and confirm your name and your prompt are both
there.

## 5. Answer the response

A file called `instructor-response.md` arrives in your repository. It acknowledges your hello
world and asks you three short questions. It is written by a script of mine that watches for
your first push, so it can take a little while to turn up, and it is not a person waiting on
the other end.

1. Open your repository page and look for the file. If it is not there yet, carry on with part
   two and come back to it.
2. Click it, then the pencil icon to edit.
3. Type an answer after each **Answer:** marker.
4. Click **Commit changes**, then **Commit changes** again.

**Checkpoint 5.** Your three answers are committed.

If the file has still not appeared by the time you have finished everything else, that is a
problem at my end rather than yours. Create a file called `help.me` in your repository, say so
in it, and carry on.

---

# Part two: Claude and GitHub

Still step by step. After this part the instructions stop naming every click, because from
there on you are making choices rather than following a path. The work does not get smaller.

## 6. Authorize the connection

1. In Claude, open **Settings**.
2. Find **Connectors**.
3. Connect **GitHub**.
4. When asked which repositories to allow, select **only** `sec-480`.

Do not choose all repositories because it is fewer clicks. Least privilege is a principle this
program has already taught you, and this is a real instance of it rather than an exercise.

**Checkpoint 6.** The connector shows as connected.

That checkpoint proves almost nothing. It is the claim the system makes about itself. The next
two are the evidence.

## 7. Prove it reads

1. In Claude, ask: *what does the README in my `sec-480` repository say?*
2. Compare the answer to what you actually wrote.

**Checkpoint 7.** Claude reports your first and last name correctly.

**Watch for this trap.** A vague question can produce a plausible answer generated from the
repository name alone, with nothing having been read. Your own name works as a test because it
cannot be guessed. If the answer is generic or hedged, treat it as a failure, not a partial
success, and ask again more specifically before moving on.

## 8. Prove it reads current content

### First, what a usage window is

A usage window is your conversation budget over a period of time. How fast you spend it depends
on how long the conversation is, how complex the work is, which features you use, which model
you are on, and how much effort you ask for. Anthropic documents this at
[How do usage and length limits work?](https://support.claude.com/en/articles/11647753-how-do-usage-and-length-limits-work).

Two things about it matter operationally, and both will bite someone this term.

**Your usage is one pool.** Work in the browser, in Claude Code, and in Claude Desktop all draws
on the same budget. Running a long agent session in the morning is why the browser is slow to
answer you in the afternoon.

**There are two windows, not one.** A session window that resets every five hours, and a weekly
cap that resets at a fixed time tied to your account. You are on Pro, so both are visible at
**Settings**, then **Usage**, along with the reset times.

**Expect the session number to read near zero right now.** It resets every five hours, so if you
have not used Claude since before class it will show almost nothing used. That is the window
working, not a broken reading. The weekly figure is the one that tells you something today.

### Then write it up

1. On GitHub, click **Add file**, then **Create new file**.
2. Name it `usage-window.md`.
3. In Claude, go to **Settings**, then **Usage**, and read both windows.
4. Note both numbers in the file, with the date and time you looked, formatted like
   `Friday 28 Aug, 2026 @ 2:15 pm`. Like this:

   ```markdown
   # Usage window check

   Checked: Friday 28 Aug, 2026 @ 2:15 pm

   Session window (5 hour): 12% used, resets 4:40 pm
   Weekly window: 31% used, resets Tuesday 2:00 am
   ```

   If a number is not shown for one of the windows, write what you saw instead of leaving it
   blank. "Session window showed no figure" is a finding, not a gap.
5. Commit it.
6. In Claude, ask it to read `usage-window.md` and tell you the numbers.

**Checkpoint 8.** A file created after the connection was authorized comes back correctly. This
is the direction almost nobody tests, and it is the one that catches a stale connection.

## 9. Write up what happened

1. Create `integration-validation.md` in your repository.
2. Write, in your own words: what you connected, what you asked to prove reading worked, what
   you asked to prove current content was reachable, and anything that failed along the way with
   what you did about it.

The failures are the valuable part. Write them down even if you fixed them in ten seconds.

What counts as evidence, and what a good write-up looks like, is in
`course/showing-your-work.md`, pushed to your repository alongside this lab. That file is worth keeping: the expectation it describes holds
for every deliverable this term.

**Checkpoint 9.** The file describes what you actually did rather than what these instructions
said to do. If those two are identical, you probably left something out, because almost nobody
gets through this without one thing going sideways.

---

# Part three: now that it works

Everything above is mandatory and everything below is not. Do these in order, and finish them
before the deadline at the top of this document. They are the first real work of the course
rather than filler, and week 2 assumes you have done them.

## Scaffold the term

You will need somewhere to put nine weeks of work. Rather than making folders by hand, ask
Claude to lay out the structure and explain its reasoning, then decide whether you agree before
you accept it.

Use `module_01` through `module_09`, matching the weeks. If Claude proposes something different,
that is worth a moment: is its structure better, or just different? You are allowed to overrule
it, and you should say why in your journal if you do.

**You know this worked when:** the folders exist in your repository on GitHub and you can
explain why they are arranged that way.

## Set up a project workspace

In Claude, create a project for this course and connect your repository to it.

The point is continuity. A project keeps context across conversations, so week 4 does not start
from nothing. This is also the first version of a question the course returns to repeatedly:
where does state actually live, and what carries forward when you close the tab.

**You know this worked when:** you can open a new conversation inside that project, ask
something about your repository, and get an answer without re-explaining what the repository is.

## If you finish all of that

Help someone next to you. Twenty-four people are doing this at once and the failures are not
evenly distributed. Debugging someone else's setup is genuinely good practice, and it is a
better use of the room than waiting.

---

# Before next week

Start this once the parts above are working. It is the first piece of work in this course that
is about judgment rather than setup.

## Break it on purpose

Ask Claude a question about your repository that it cannot possibly answer correctly. Ask what
is in a file that does not exist. Ask how many commits you made last Tuesday. Ask what your
teammate wrote, when you have no teammate. Ask it to summarize a file you never created.

Watch what comes back. Sometimes you get a clean "I do not have that." Sometimes you get a
confident, specific, entirely invented answer. Both outcomes are worth seeing, and the second
is the one that will cost you if you meet it for the first time inside real work rather than
here, where you already know the truth.

Try at least three different questions, because the behavior is not consistent and one attempt
tells you very little.

Write up in `integration-validation.md`: what you asked, what came back, and, for each one,
whether you could have detected the problem if you had not already known the answer.

That last question is the entire course in one line. Keep your answer to it. We open week 2
with it.

## Also before next week

- A working copy somewhere permanent, with checkpoint 3 satisfied.

---

## Done when

- [ ] Claude and GitHub accounts confirmed, plan noted
- [ ] `sec-480` exists, private, README has your first and last name
- [ ] Instructor invited, acceptance is automatic
- [ ] `hello-world.md` created and committed, contents verified in the browser
- [ ] Response answered and committed
- [ ] Connector authorized
- [ ] Reading validated with a question only a reader could answer
- [ ] Current content validated with a file made after authorization
- [ ] `integration-validation.md` written in your own words

Before week 2, if you have the time:

- [ ] `module_01` through `module_09` scaffolded
- [ ] Course project workspace created and connected to your repository

Before week 2, not optional:

- [ ] A working copy somewhere permanent, with git tracking the folder you work in
- [ ] `journal/module-01.md`, the first journal entry, all five headings

The journal is not part of this lab, it has its own brief, and week 1 is not complete
without it. `M01_brief_journal.md` carries the detail. **There is no survey for module 1.**

## When it does not work

**Symptom** | **Usually means** | **Try**
------------|-------------------|--------
Nothing shows as a change | You are working outside the repository folder | Look for `.git` in the folder you are editing in
Push is rejected | Credentials. GitHub stopped accepting account passwords for git operations | Use a personal access token, or an authenticated client like GitHub Desktop
File is on GitHub but empty | Created but never saved before committing | Save, commit, push again
Claude cannot see the repository at all | Authorization did not include this repository | Reopen connector settings and check which repositories are in scope
Claude describes a repository that is not yours | You have more than one and it picked another | Name the repository explicitly in your request
Claude answers about the README without quoting it | Nothing was read, an answer was generated | Ask for exact text only a reader would have
The new file is not visible | Cached view, or the file was created on a branch | Confirm the file exists on your default branch in the browser first
Invite shows sent, instructor sees nothing | Wrong account, or an unaccepted invite | Confirm the exact username with me and resend

## The two that cannot wait

Two things, the same two from the top of this document: the instructor invited, and
`hello-world.md` committed. Get those done even if every later checkpoint is unfinished.
Everything in week 2 depends on that access existing.

If either one is not working, tell me as soon as you know. A broken invite found on Friday
costs you a week. Found now it costs both of us two minutes, and `help.me` is the fastest way
to reach me.

## When you are stuck: `help.me`

There is a channel that works even when nothing else does.

In your repository, on GitHub, in the browser, create a file called `help.me` and describe your
problem in plain words. Not correct terminology, just what you are seeing. "It keeps asking for
a password and then fails" is a perfect help request.

Shortly, within minutes, a `help-response.md` appears in your repository with guidance aimed at
what you described. I see it too, and I will address it.

This works with no git client, no connector, no installs, and nothing configured. If you can
reach GitHub in a browser, you can reach help. Use it rather than sitting quietly, and use it
again later in the term whenever something has you stuck.

## If it all goes sideways

Work down this list. Each step assumes the one above it failed.

1. **Browser only, on the workstation.** Covers both required items with no installs and no VM.
   This is the fallback, and it is also a perfectly good primary path.
2. **View Portal.** If you need a real git client on campus and cannot build a VM. Remember it
   resets, so treat it as a workspace rather than a home.
3. **Build a VM here.** Slower today, better every week after, and it persists on the
   workstation you built it on.
4. **Create `help.me`** in the browser, describing what you see. See the section above.
5. **Nothing is working at all.** Come find me rather than burning the session. That is not
   failure, it is the correct escalation, and setup problems in week 1 are common enough that I
   have planned time for them.
