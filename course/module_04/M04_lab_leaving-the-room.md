<h3 align="center">SEC 480: Advanced AI Practicum</h3>

# What changes when you leave the room

**Due:** Thursday 1 October, 9:00 pm.

## The situation

Same service desk, same server, same person. Dana Okafor in Finance, ticket **SD-4680**, the
`\\fs02\finance\Q3-working` folder, forty quarter working papers.

Module 3 was that incident handled once, by hand, by you. What arrived this week is different:

> This is the fourth time this quarter. Make it not need you.

That sentence is the whole module. Nobody is asking for a better answer. They are asking for
an answer that arrives when you are not there.

## What is actually different, and it is not the tooling

Module 1 asked whether the connection works. Module 2 asked whether the output is true. Module
3 asked whether you can design where the platform sits in a piece of work. All three had your
hands on the work the entire time.

This unit takes your hands off it, and **the thing that changes is where failure lives.**

| | You do the work | You direct the work |
|---|---|---|
| How it fails | You get it wrong | It goes wrong and you do not notice |
| When you find out | While you are looking at it | When somebody else finds it |
| What protects you | Checking your answer | Deciding in advance what you would check |

The second column is a different skill and it is the one this unit teaches. It is also the
failure this course keeps coming back to: **the system reports success and the thing you
wanted did not happen.**

## How this lab works

Four acts, in order, because each one leaves the next one something to run on. **An act is one
of the numbered sections below**, and each one states what it is worth and how you know it
worked.

**Project 1 comes first.** This lab carries forward the Project, instructions and Skill you
built for it. A **Project** is the place in Claude where instructions live so they survive
between conversations; `course/module_03/M03_lab_repeatable-work.md` covers it. If Project 1 is
not finished, finish it before starting act 2.

**Eleven checks are marked through the acts, CP1 to CP11.** Each names the thing it looks at
and what it is worth. They exist so that what is being assessed is not a mystery. They are not
a substitute for reading the acts.

Everything you produce goes in `module_04/` on a branch. Act 1 sets that up.

**Everything graded here works in a browser.** No install, no administrator, no desktop
application required. If you are running the desktop application, nothing below breaks, but it
is an option rather than the default.

---

## Act 1: plan it (3 points)

Unit 2 is about work that runs when you are not there. The first habit of directing work is
deciding what it is before anything happens, and writing that down where somebody else can see it.

### The tracking, first

`Milestone_02` is already in your repository. It holds all of unit 2: modules 4, 5, 6 and
Project 2. If you cannot find it, make one by hand with that name; nobody is marked down for it.

```bash
git switch -c module_04
mkdir -p module_04
```

Then, through the connector or on GitHub directly, four issues in GitHub, one for each act.
Each one:

1. has a title and a sentence saying what it covers,
2. is attached to `Milestone_02`,
3. is assigned to you,
4. carries the label `Lab_M04`, which should already exist in your repository (if it does not, create it with exactly that name); modules 5 and 6 use `Lab_M05` and `Lab_M06` the same way,
5. says in its text that it is due **Thursday 1 October, 9:00 pm**. An issue in GitHub has no
   date field of its own, and the milestone holds a date but not a time, so the text is where
   the deadline lives.

All four exist before the first commit of real work. The commit history shows the order, so do
not backfill it.

### Then one question, in writing

In `module_04/account.md`, in your own words: what can **you** see of a piece of work before it
runs, while it runs, and after? Not what the system knows. What you, the person, can actually
look at: a screen, a file, a message. Not a feature list.

> **CP1 (1 point).** Four issues in GitHub, each attached to `Milestone_02`, assigned to you,
> labelled `Lab_M04`, and stating the due date Thursday 1 October, 9:00 pm.
>
> **CP2 (1 point).** All four issues were **created before the first commit of real work**.
>
> **CP3 (1 point).** `account.md` says, in your own words, what you can and cannot see of a
> piece of work before, during, and after it runs.

**You know it worked when** the four issues show under `Milestone_02` with you as assignee, the
`Lab_M04` label and the deadline in their text, and `account.md` is committed after them.

**Produces:** four issues in GitHub, `module_04/account.md`, and a branch.

---

## Act 2: give it a home (2 points)

Project 1 asked you for three things you now carry forward: a Project, the instructions you
wrote into it, and one Skill, a named procedure with the question supplied when it runs rather
than baked into it. A Skill sitting in a conversation you had once is a procedure nobody can
reach. This act makes it reachable: saved, callable by name, and run from inside your Project.

### If you have your Project 1 work

Use it. Bring the Project and its instructions forward. Nothing needs to be rewritten for this
act, but the Skill has to be **saved**, not just attached.

**Attaching a Skill file to a chat does not install it.** That chat can read and follow the file,
and nothing else can: a scheduled task will not see it. To save it:

1. In a chat inside your Project, attach your Skill file.
2. Ask Claude to save it as a reusable skill.
3. Accept the **Skill proposal** card. It then reads **Saved as /your-skill-name**.
4. Check it: open a **new** chat in the Project with nothing attached, and type
   `/your-skill-name`. If it runs, it is saved.

The scheduled task in act 3 calls the Skill the same way, by its name.

### If Project 1 is not finished

Finish it first. Acts 2 and 3 build on your Project 1 work: the Project, its instructions, and
the Skill. There is no shortcut version here, because a Project and Skill built in a hurry for
this act would not be the thing worth leaving to run unattended.

### The check that is the actual work

A Project can hold your instructions, show you a settings screen with everything in place, and
still not apply all of them. Project 1 asked for this check. Do it again here, because a Project you
are about to walk away from is a worse place to be wrong.

This check is a **read-back**: you ask the system to tell you what it has stored, and compare
that with what you gave it. Start a fresh conversation inside the Project, paste nothing, and ask it to repeat the
instructions you wrote for the Project back word for word, without summarizing. Compare word for word against what you wrote.
Write what came back, and what was lost if anything was lost, into `module_04/project.md`. At the
top of that file, name your Project and the name your Skill is saved under.

> **CP4 (1 point).** A Project exists with its instructions, and your Skill is saved and runs by
> name in a new chat with nothing attached. `project.md` names both.
>
> **CP5 (1 point).** `project.md` shows the read-back: what you asked, what came back, and
> either what was lost or a plain statement that nothing was.

**You know it worked when** a conversation started fresh inside the Project, with nothing
pasted in, repeats your instructions back and you have compared them word for word: either they
match, or `project.md` says exactly what changed.

**Produces:** `module_04/project.md`, and a Project holding your Skill.

---

## Act 3: leave it running (5 points)

This is the largest act in the module and it is where your hands come off.

You are going to set the procedure to run at a time you choose, on a schedule, bound to the
Project from act 2, and then you are going to close everything and go and do something else.

### Setting it up

A **scheduled task** is work set to run at a time you choose, whether or not you are there to
watch it. In Claude's left sidebar, open **Scheduled** and create one; the form is headed
**Create scheduled task**.
It asks for a name, the instructions it runs, **Work in a project or folder** (choose your act 2
Project), a **Frequency**, and permissions, with more under **Advanced settings**.

**Frequency starts at Manual.** Manual only runs when you start it yourself, so it is not a
scheduled task for this act. Choose **Hourly** or longer: the options are Hourly, Daily,
Weekdays, Weekly and Monthly.

**The model menu starts at Default model.** Change it to a named model. "Default model" does not
tell you, or anyone reading your write-up later, what actually ran.

**One of those is a decision rather than a form field**, and it is the one being marked:

> **Which model?** What does this work actually require, given that nobody will be reading the
> result as it appears, and nobody will notice if it is thin?

You are not answering that from a table of specifications. You are answering it by trying it.

### Compare two, then choose

Run the same instructions twice, once on each of two models, while you are sitting there
watching. Use two ordinary chats inside your Project and change the model in each chat's model
menu before you send. Same Project, same wording, nothing else changed. Then read both.

Write it up in `module_04/schedule.md` **before** you schedule anything, as three short parts:

1. **What you asked**, once. The same text both times.
2. **What differed.** Not "one was better". Name the difference you can point at: something one
   noticed and the other did not, something one stated as certain that the other qualified, a
   step one took and the other skipped, or a length difference that did or did not carry more
   information.
3. **Which one you are scheduling, and what you gave up to pick it.** Every choice here costs
   something. A model that reasons harder over work nobody reads may be spending more than the
   work is worth. A lighter one may be exactly right, or may be thin in a way you will not be
   present to catch.

If the two outputs are hard to tell apart, that is a finding and it is worth saying. It means
the difference does not matter for this work, which is useful to know and is itself a reason to
pick one.

**Your reason is written before the run.** A reason written after you have seen the scheduled
output is a description of the output.

**Anything other than Manual repeats until you stop it.** Hourly is the shortest repeating
frequency. Pick one, note what you picked, and **write down how you turn it off**, because a task that repeats is a task that keeps being wrong
after you stop paying attention to it.

### The line on the screen worth reading twice

Under **Permissions**, the task is set to **Automatically approve**. Find every place the
product describes what that means, and write each one down word for word in `schedule.md`.

There is more than one, and they do not say the same thing.

Read them against each other, because one of them is doing more work than it appears to. Nobody
is checking while the work happens. Either the only thing standing between an unattended run and
a bad outcome is the platform's own judgement about what **looks** unsafe, in a situation you did
not anticipate and are not present for, or there is no pause at all. Those are different
promises.

Then write one sentence: **which of those sentences are you relying on, and how would you know
which one is true?**

### Then leave

Set it running. Close the conversation. Do something unrelated, somewhere else. Come
back after it has fired at least once.

**Then turn it off.** Open **Scheduled** in the sidebar, open your task, and switch its toggle
to **Paused**. Deleting it also stops it. One run is all this act needs, and leaving it on means it keeps running
long after you have stopped reading it.

### What to write down when you come back

In `schedule.md`:

* When it was due to run, given the frequency you chose, and the time it actually ran. **Read
  that time from the task's own history, not from the output.** A run's report of its own start
  time can be wrong, which is this module's whole point in one line.
* What came back.
* **What you cannot tell from the result.** This is the part that carries the act. You were not
  there. So: did it read everything you inferred it read? Did anything fail quietly partway
  through and get reported as finished? What would the output look like if it had, and how
  would that differ from what you are looking at?

> **CP6 (1 point).** A scheduled task exists, with a name, instructions, and the act 2 Project
> attached.
>
> **CP7 (2 points).** `schedule.md` compares two models on the same instructions, naming a
> difference that can be pointed at, and says which one is being scheduled and what was
> given up to pick it. Committed before the run.
>
> **CP8 (1 point).** `schedule.md` shows it ran on its schedule while you were not watching:
> when it was due, when it actually ran (read from the task's history), and what came back.
>
> **CP9 (1 point).** `schedule.md` says what you cannot tell from the result, in your own
> words, naming at least one thing that could have gone wrong without changing how the output
> looks. It includes the approval sentences quoted word for word, the one sentence on which you
> are relying, and how you turn the task off.

**You know it worked when** you come back to a result you did not watch arrive, produced at the
time you set.

**Produces:** `module_04/schedule.md`, and a scheduled task bound to your Project.

---

## Act 4: hand it over (2 points)

Something is now running without you. In six weeks you will have forgotten what it relies on.

A **handover** is a note that lets somebody take over a piece of work without having to ask you
anything. Write `module_04/handover.md` for the person who inherits this, which is you, later. It is one
page and it answers four things:

1. What this runs, on what schedule, and what it is for.
2. What it relies on being true. Every one of those is a place it can go wrong quietly.
3. **How somebody would know it had stopped working.** Not "an error appears", unless you can
   say where it appears and who sees it. If the honest answer is that nobody would know, write
   that. It is the most useful sentence in the document.
4. What you would change first.

**Nobody else acts on this document.** It is not reviewed, not assigned, and not sent anywhere.
It goes in your repository alongside the rest of the work and it is graded there.

> **CP10 (1 point).** `handover.md` covers all four questions.
>
> **CP11 (1 point).** Question 3 is answered concretely: where a failure would show, who would
> see it, or a plain statement that nobody would.

**You know it worked when** you can read `handover.md` as if you had never seen the Project,
and it tells you what the task does and how you would find out it had stopped.

**Produces:** `module_04/handover.md`.

---

## What is due

On the `module_04` branch, in a pull request.

**The pull request is a container and nobody opens it.** It is not reviewed, nobody is assigned
to it, and you do not need to wait on anyone before or after you open it. It exists so that the
whole module arrives as one thing with a description you wrote. Open it, describe what is in it,
and you are finished.


- [ ] `account.md`, saying what you can and cannot see before, during and after
- [ ] four issues in GitHub, created before the work, attached to `Milestone_02`
- [ ] `project.md`, with the read-back
- [ ] `schedule.md`, with the two-model comparison and the choice committed before the run,
      both approval sentences quoted from your own screens, which one you are relying on, how you
      turn the task off, the times, and what you cannot tell
- [ ] `handover.md`, the four questions

Alongside each of those, the working that produced it. `course/showing-your-work.md` covers
what that means. A correct file with no visible working does not get full credit, and a wrong
file with clear reasoning does not lose it all.

**The journal is a separate deliverable**, worth 6 points on its own, due at the same time. It
is in `M04_brief_journal.md`.

## When it does not work

**You cannot find a scheduling option at all.** Say so in `schedule.md`, say what you looked at,
and add a `help.me` file. A response comes back in your repository, usually within a few hours,
and it works even when nothing else does. You are not marked down for a control your account
does not have.

**The scheduled task runs immediately instead of at the time you set.** Write down that it did.
That is a real observation about where the work actually happens, and it still earns CP8 when
you have written it down.

**It ran and produced nothing useful.** Good. That is act 3's question answered for free. Write
what came back and what you cannot tell from it.

**The scheduling screen offers only one model.** Say so in `schedule.md`, name the model it
offered, and move on. CP7 is credited in full when you have written that down.

**The two models produced almost the same thing.** Say so, and say what you compared. That is a
real result about this work, not a failure to find one, and it earns the same credit.

**You have no Project or Skill from Project 1, or it does not work.** Finish or fix Project 1
first. Acts 2 and 3 depend on it.

**The read-back in act 2 shows your instructions came back changed.** That is a finding, not a
failure. Write what was lost, rewrite the instruction, and read it back again.

**Something else.** Add a `help.me` file to your repository describing where you are stuck, and
push it.
