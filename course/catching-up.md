<h3 align="center">SEC 480: Advanced AI Practicum</h3>

# Catching up

**Reference, for anyone joining the course after it started or coming back after time away.**

You are behind. That is the whole of the bad news, and it is a smaller problem than it looks
from here.

This document is the order to do things in. It has been trimmed: some of what the class did is
not being asked of you, and where that is true it says so and says why. What is left is the
work that later modules genuinely stand on.

## The dates in this document are the ones that apply to you

Course material is going to arrive in your repository with deadlines printed at the top of it,
and those deadlines have already passed. They were right for the class and they are not right
for you.

**The table at the end of this document replaces every date printed in `course/module_01/` and
`course/module_02/`.** Read the material for what it asks you to do. Read your dates here.

---

## Why this course looks different from your others

Three things surprise people, and knowing them now saves you guessing.

**Your repository is the classroom.** Work that is not pushed does not exist. There is no
upload box anywhere. Everything you hand in, you commit.

**How you got there is graded alongside what you got.** Prompts, what came back, what you
checked, what you abandoned. A correct answer with nothing showing how you reached it does not
get full credit, and a wrong answer with clear reasoning does not lose all of it. There is a
short reference on this called `showing-your-work.md`, and it arrives with your material.

**There is a help channel that works when nothing else does.** It is described at the end of
this document. Use it early rather than sitting stuck.

---

## Stage 1: the two that come first

Nothing else in this course can reach you until these two are done, including the material
every later stage refers to. Neither needs anything installed and neither needs anything
connected. A browser and a GitHub account is the whole list.

**1. A private repository, with your instructor invited.**

* Sign in at `github.com`.
* Create a new repository named **`sec-480`**. The hyphen matters. Capitals do not, so `SEC-480`
  is fine too.
* Set it to **Private**.
* Tick **Add a README file**.
* Edit `README.md` so it holds one line: your first and last name, then the course. For example
  `Rose Davis, SEC 480`. Use the name as it appears on the class roster rather than a nickname,
  because course tooling reads this line to work out whose repository it is. If you are not sure
  which form that is, the **People** section of the Canvas shell for this course is the one to
  match.
* Go to **Settings**, then **Collaborators**, then **Add people**, and invite the username of your
  instructor, derp-cc. 

Acceptance is automatic. There is nothing to wait for and nothing to ask about.

**The repository name matters more than it looks.** The tooling that hands out material, answers
help requests, and reads your progress looks for `sec-480`, in any capitalisation, and nothing
else. A repository called something else is invisible to all of it. If you have already made one
under another name, it is not a disaster: renaming on GitHub keeps your history, keeps the
collaborator, and redirects the old address. It costs you a step, and several people this term are
in exactly that position.

**2. `hello-world.md`, committed.**

Ask a platform to help you write a short markdown file introducing yourself, with these
labelled lines in this order:

* `Name:` your first and last name
* `Program:` your program
* `Graduating:` the year you expect to graduate, four digits
* `Want from this course:` a sentence or two, honest rather than impressive
* `Something I do well:` one sentence, and it does not have to be technical

On GitHub, use **Add file**, then **Create new file**, name it `hello-world.md`, and paste the
result in. Underneath it add a heading `## The prompt I used` and paste the exact text you typed,
as written, including any typos. Then commit.

The labels matter because a script reads them.

**You know stage 1 worked when:** your repository page shows `Private`, the README shows your
first and last name, and you can open `hello-world.md` and read your own text in it. Seeing the
filename in a list is not the same as reading the file. Open it.

### What happens next

**One thing arrives on its own.** Within a few hours of that first push, `instructor-response.md`
turns up in your repository: an acknowledgement with three short questions in it, written by a
script rather than by a person waiting. Answer them by editing the file and committing it. That
is the last piece of stage 1.

**The course material is placed by hand**, by your instructor, once your repository exists.
Modules 1 and 2 come first, in a `course/` directory, with a copy of this document beside them at
`course/catching-up.md`. Module 3 and Project 1 follow after you and your instructor meet, which
is the step between stage 3 and stage 4 below. That directory is your instructor's. The rest of
the repository is yours.

If the material has not turned up and you are ready for it, say so through the help channel at
the end of this document rather than waiting. It is not automatic and nobody will know you are
waiting unless you say.

---

## Stage 2: module 1

**All of it.** Module 1 is short, and it is the foundation every later module stands on, so
nothing has been cut from it.

The lab is at `course/module_01/M01_lab_setup.md` and it walks through each step. Two of its nine
checkpoints you have already done in stage 1. Here is what the rest are actually for, so you are
not following steps blind.

| Checkpoint | What it proves |
|---|---|
| 1 | You can reach both accounts, and you know which plan you are on |
| 2, 3, 4 | Done in stage 1. Repository, invite, hello world |
| 5 | You answered `instructor-response.md` |
| 6 | The platform is authorized against your repository |
| 7 | It can actually read what is in there. Your own name is the test, because it cannot be guessed |
| 8 | It can read content created **after** it was authorized. This is the direction almost nobody tests and the one that catches a stale connection |
| 9 | `integration-validation.md`, written in your own words: what you connected, what you asked, what failed and what you did about it |

Checkpoints 6, 7 and 8 are the connection, and there is a section on that below, because it is
the part of module 1 that gave the class the most trouble.

**Also module 1:** the journal, at `journal/module-01.md` in your repository, briefed in
`course/module_01/M01_brief_journal.md`. Part one asks four questions about where you are
starting from. **It is not graded**, and it is still the part worth writing: those answers shape
the examples you get for the rest of the term. There is no survey for module 1.

**Skip:** part three of the lab, the term scaffold and the project workspace. Useful, not
load-bearing, and you can pick them up whenever.

---

## Stage 3: module 2

**Trimmed, from four acts to three.** This is the one place real work has been taken off you,
and it is worth knowing what and why.

The situation: somebody left, you have their job, and they left you a note, a ticket and twenty
lines of log that do not add up. The lab is at `course/module_02/M02_lab_the-handoff.md` and the
files are in `course/module_02/M02_handoff/`. Read all three of those before anything else.

| Act | Status | What it is |
|---|---|---|
| **Act 1** | **Required** | Write down how you actually work, by being interviewed about it rather than from a blank page. Produces `process.md` |
| **Act 2** | **Required** | Run that process on the log in a fresh conversation and save the whole exchange. Produces `analysis-session.md`. It deliberately does not produce a verdict |
| Act 3 | **Optional** | Take the analysis apart claim by claim and amend your process where it let something through |
| **Act 4** | **Required** | Write the finding, build the tracking, and hand the work on through a pull request |

**Why act 3 is the one that comes out.** It is the longest act, and module 3 asks you to do the
same thing again, live, with a harder set of evidence. Doing it twice inside one week, once
alone and cold, buys you very little. If you have the appetite for it, do it, and it will make
act 4 better. Nobody is counting it against you if you do not.

**Act 2 stays even though it is small**, because act 4 asks you what your analysis claimed that
the evidence did not support. Without act 2 there is no analysis to answer that about.

**Also module 2:** the journal, at `journal/module-02.md`, briefed in
`course/module_02/M02_brief_journal.md`. Its five questions map onto the acts. Answer the ones
for the acts you did and say plainly that you skipped act 3 in the ones that do not apply. An
honest "I did not do this one" is a complete answer here and costs you nothing.

---

## Before module 3: meet your instructor

**This one is not optional and it is not a telling-off.**

Once module 2 is in, and before you start module 3, sit down with your instructor. Office
hours or a call, whichever suits.

The reason is specific. Modules 1 and 2 you can work from a lab sheet on your own, which is why
they come first. Module 3 is a five-act lab that the rest of the class worked through in a
staffed session with your instructor circulating the room, and there is no session between now
and when yours is due. That meeting is the nearest equivalent, and it is worth more than any
amount of reading.

Bring what you have, and bring what is not working. The second one is more useful than the first.

> **Time and place:** to be arranged. Reach out once module 2 is in.

---

## Stage 4: module 3 and Project 1

**Same work as everybody else, same standard.** Nothing is trimmed here, because this is where
you rejoin the class rather than catch up to it.

**Module 3** is `course/module_03/M03_lab_the-crossing-point.md`. Five acts, twelve checks
marked through them so you can see what is being assessed. Read
`course/module_03/M03_brief_before-class.md` first, and do the connection check it describes
early: it is not graded, and it hands you two of the twelve checks before you start.

Act 1 is the one people misread. It asks you to set up the tracking **before** any real work
exists: five issues in GitHub, one per act, each with an owner and a date, attached to
`Milestone_01`. **No board is needed**, and you may see one mentioned in older material: it was
dropped on Thursday 18 September because the connector cannot create one. The commit history is what shows you did it in that order,
so it cannot be backfilled. That ordering is the exercise rather than admin.

On the name: **issues in GitHub** are not problems to fix, despite what the word suggests. They
are GitHub's own message threads, attached to your repository, and they are how work gets
tracked and assigned. That naming accident catches nearly everybody.

**Project 1** is `course/module_03/M03_project.md` and it is due on the same date as the rest of
the class. It is the largest single piece of the unit. The tracking you build in module 3 act 1
is the thing that will tell you whether you are behind on it, which is why that act is worth as
much as it is.

Also in module 3: the journal at `journal/module-03.md`, and the survey at
`surveys/module-03.md`. **Submitting the survey is worth points and not submitting it costs
them**, so do not skip it. What you put in it is never evaluated: there is no right answer and an
honest low rating is worth more than a generous one.

---

## Connecting a platform to your repository

Module 1 asks you to prove a platform can read your repository. This is the part that gave the
class the most trouble, so here is the short version of what was learned.

**Try the command line tool first.** Most people who fought with the browser connector got it
working immediately this way instead. Install it, point it at a local copy of your repository,
and ask it questions about what is in there. It reads the files on disk, so there is no
authorization step to go wrong.

**The browser connector is the alternative.** In the platform's settings, find connectors,
connect GitHub, and when it asks which repositories to allow, select **only** `sec-480`. Not all
of them because it is fewer clicks. Least privilege is a principle this program has already
taught you and this is a real instance of it.

**Then prove it, twice, because a connected badge proves nothing.** It is the claim the system
makes about itself.

1. **It reads.** Ask what the README says. Your own first and last name is the test, because it
   cannot be guessed from the repository name. A vague or hedged answer is a failure, not a
   partial success.
2. **It reads current content.** Create `usage-window.md` **after** authorizing, put your usage
   figures in it with the date and time you looked, commit it, then ask the platform to read
   those numbers back. A file made after the connection was set up is the one that catches a
   stale connection.

**If you cannot get it working, you have not failed the module.** A documented failure passes
these checkpoints. What earns the pass is a specific, checkable account in
`integration-validation.md`: what you tried, what each screen said, and where it stopped. "It
did not work" does not. An empty file does not.

Two known causes that are nobody's fault: a workspace whose connector list has no GitHub entry
at all, which no student can change, and a connection that reports itself connected in settings
while the conversation is not actually using it.

---

## When you are stuck: `help.me`

There is a channel that works when nothing else does.

In your repository, in the browser, create a file called `help.me` and describe the problem in
plain words. Not correct terminology, just what you are seeing. "It keeps asking for a password
and then fails" is a perfect help request.

A `help-response.md` appears in your repository with guidance aimed at what you described, and
your instructor sees it too.

This needs no git client, no connector, no installs, and nothing configured. If you can reach
GitHub in a browser, you can reach help. Use it early, and use it again later in the term
whenever something has you stuck.

---

## Your dates

Everything is due at **9:00 pm** on the day named.

| What | Due |
|---|---|
| **Stage 1** | **Done.** Repository, hello world and the response are all in |
| **Module 1** | **Sunday 28 September, 9:00 pm** |
| **Module 2** | **Thursday 2 October, 9:00 pm** |
| Meet your instructor | Between module 2 and module 3, and the sooner the better |
| **Module 3** | **Tuesday 7 October, 9:00 pm** |
| **Project 1** | **Thursday 9 October, 9:00 pm** |

**Project 1 no longer lands with the class.** The 11 September plan had you level by the start
of unit 2, and that was written when there was time for it. Starting from here, holding that
date would mean modules 1, 2 and 3 plus the project inside a week, from nothing. These dates are
the honest version instead.

**Unit 2 runs while you do this**, and its work is not in the table above. That overlap is the
real cost of the late start, and how to handle it is the first thing to raise when you meet.

These replace every date printed in the module 1 and module 2 material.

---

## Done when

**Stage 1**

- [ ] `sec-480` exists, private, README carries your first and last name
- [ ] Instructor invited
- [ ] `hello-world.md` committed, contents read back in the browser
- [ ] `instructor-response.md` answered and committed

**Module 1**

- [ ] Both accounts confirmed, plan noted
- [ ] Platform authorized against the repository
- [ ] Reading proved with a question only a reader could answer
- [ ] `usage-window.md` created after authorizing, and read back
- [ ] `integration-validation.md` in your own words, including anything that failed
- [ ] `journal/module-01.md`, both parts

**Module 2**

- [ ] `process.md`, from act 1, and the interview that produced it
- [ ] `analysis-session.md`, from act 2, the whole exchange
- [ ] `finding.md`, from act 4
- [ ] `Milestone 1` and issues in GitHub for the acts you did
- [ ] A pull request whose description is a real handover, merged into your primary branch
- [ ] `journal/module-02.md`

**Module 3 and Project 1**

- [ ] Met with your instructor
- [ ] Module 3, all five acts, CP1 to CP12
- [ ] `journal/module-03.md` and the module 3 survey
- [ ] Project 1

Alongside all of it, the working that produced it. Prompts, what came back, what you changed and
why. That is not an extra, it is part of what is graded.
