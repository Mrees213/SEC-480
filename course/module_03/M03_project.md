<h3 align="center">SEC 480: Advanced AI Practicum</h3>

# Project 1: a tracked deliverable, an analysis you argue with, and a chain that works

**Assigned:** module 3, Friday 11 September.
**Due:** Thursday 24 September, 9:00 pm.
**Weight:** the largest single piece of Milestone 1.

**You get two weeks for this, and the reason is Friday 18 September.** That is a no-class day,
so the middle Friday of this project is free working time rather than a session.

The cost of that is there is no meeting between now and the due date. Nobody will tell you you
are behind. The tracking you set up in the first week is the only thing that will, which is why
Part 1 is worth 25% of a project that is otherwise about analysis.

## What this is

One piece of work with three parts, on a subject you choose. The three parts are the three
things this unit taught, and they are assessed together because separating them would let you
avoid the hard one.

1. **A deliverable, tracked.** Something real that you produce, planned and tracked in GitHub
   with owners, dates, and a definition of done.
2. **An analysis you argue with.** A platform analyzes something inside your subject, and you
   produce a critique that separates what it stated from what it inferred, and says what the
   evidence actually supports.
3. **A chain that works.** One small task that crosses two systems end to end, with a
   prediction of where it would fail written before you ran it.

## What module 3 gave you, and where each piece goes

Nothing here is new work. Every part of this project is something you did a small version of
already.

| From module 3 | Used here as |
|---|---|
| Act 1, planning before working | Part 1's tracking, on your own subject rather than the lab's acts |
| Act 2, the second system connected and validated | Part 3's chain has somewhere to cross to |
| Act 3, `prediction.md` and the comparison | Part 3, same shape, your own task |
| Act 4, the claim table and `Cannot determine` | Part 2, same format, your own material |
| Act 5, the tagged finding and the reviewed pull request | Part 2's finding, and how the whole project is submitted |
| `M03_lab_repeatable-work.md` | The three requirements below. Read it before you start |

**This project assumes acts 1 through 5 are done.** If they are not, start there. Part 1 needs
the issues, Part 2 needs the claim table format, and Part 3 needs the second system connected.
Beginning here instead will cost you an hour and send you back anyway.

## Three requirements that run across all of it

These come from `M03_lab_repeatable-work.md`. They are requirements of the project, not a
fourth part, and each one is assessed inside the part it belongs to.

1. **Work inside a Project, and prove it is applying your instructions.** Include the verbatim
   read-back and say what, if anything, came back different from what you wrote.
2. **Write an output contract before you see any output.** Columns, permitted values, required
   sections. Then say what came back that did not match it.
3. **Build one Skill and show it passes the reuse test.** It has to run on work it was not
   written for, without editing. Show the check, not just the Skill.

A Skill with no reuse check, a contract written after the output, or a Project with no read-back
are each the same failure: the artifact exists and the thing it was for did not happen.

## Choosing your subject

Pick something you actually care about. Your capstone direction is a good source, and so is
anything from an earlier course you never finished properly.

**The constraints on your choice:**

* It has to contain something analyzable. A log, a configuration, a codebase, a policy document,
  a dataset. Something with claims in it that can be checked.

  **You do not need a capstone, a job, or a live project.** Any of these work: a configuration
  file from your own lab, code you wrote for an earlier course, a public policy document, a
  README checked against the code it describes, a Dockerfile, a package manifest, a CI
  workflow, a vendor security page, or a small public dataset with its data dictionary.

  Steer away from anything that has to be run rather than read. If checking a claim means
  executing something, the checking stops being line by line and the table stops being
  provable.
* It has to be small enough that you can read the whole thing twice in one sitting. Module 3's
  evidence packet was about 100 lines across four files, and that is a fair target: roughly 50
  to 150 lines, or one to three pages. A scoped-down piece of a large interest beats an
  unscoped version of a small one. One module of a codebase is the project; the codebase is
  not.
* Nothing sensitive. No real credentials, no personal data, no material from a workplace that
  has not agreed to it. `course/showing-your-work.md` covers what goes into a repository, and
  this is where it matters most, because your working sessions are part of the submission.

If you are not sure whether your subject works, ask before you start rather than after.

## Part 1: the tracked deliverable

Plan and track the work in GitHub, the way act 1 did it: before the work, not after.

**What has to exist:**

* Issues in GitHub for the work, with owners, dates, and enough description that someone else
  could tell when one is done.
* Those issues attached to `Milestone_01`.
* Issue states that reflect reality at the point you submit, not at the point you set them up.
* A definition of done for the deliverable itself, in `definition-of-done.md`, written before
  you started building.
* **Issues closed by commit reference**, `Closes #12` in the commit message, rather than closed
  by hand.

**What is assessed:** whether the tracking describes the work that actually happened. The commit
history and the issue close times are what show this. Tracking filled in the night before, in one
pass, reads exactly like what it is.

**No board is required.** Dropped Thursday 18 Sep, 2026: the connector cannot create one. Issues
and the milestone carry the tracking on their own.

## Part 2: the analysis you argue with

Have a platform analyze something in your subject. Then take it apart using the same table you
built in act 4 of module 3: `id`, `claim`, `evidence`, `type`, `verdict`.

**The method carries over from that lab. The material does not.** Act 4's source was a log
because the scenario was an intrusion. Yours will be whatever your subject is made of.

The two rules from that table hold here:

* Every `evidence` cell is a **verbatim quotation** from your own source material, or the
  literal `NO EVIDENCE` on a row typed `unsupported`.
* `type` is exactly one of `stated`, `inferred`, `unsupported`.

Then a section headed exactly `Cannot determine from this evidence`. If nothing is missing,
write the heading and the single word `Nothing`.

Then write the finding. Half a page, for someone who has not seen your material and will not
read it. **Every factual sentence outside the cannot-determine part carries a tag** back to the
row it rests on, `[C3]`, and no tag may point at a row you typed `unsupported`.

**What is assessed:**

| Assessed | Not assessed |
|---|---|
| Whether the claim types are right | Whether the analysis was good |
| Whether your verdicts have reasons rather than restatements | Whether you found a specific number of problems |
| Whether every quotation is findable in your source | Whether the conclusion is impressive |
| Whether the finding says what the evidence supports and stops there | |
| Whether you gave credit where the analysis was right | |

An analysis you found nothing wrong with is an acceptable result if you can show how you looked.
An analysis you disagreed with everywhere, without reasons, is not.

## Part 3: the chain

One task, crossing two systems, working end to end. Small is fine. Useful to you is better than
elaborate.

**Before you build it, write down where you expect it to fail.** In `chain/prediction.md`,
before any of it works. Name the step, and say why that step is the fragile one. The commit
history is the evidence that it came first.

Then build it, and write up what actually happened. If your prediction was wrong, that is a
result and it is worth as much as being right, as long as you can say why you expected
differently.

**What is assessed:** the prediction and the comparison. A working chain with no prediction is
worth less than a chain that broke where you said it would.

The reason is the thing this whole unit has been circling. Every system in the chain reports its
own step succeeding. Nothing reports that the handoff between them did nothing. Knowing in
advance where you cannot trust a success message is the skill.

## What to submit

In your repository, on a branch, through a pull request **with your instructor as reviewer.**

```
project-01/
  README.md              what this is, what you chose, and why
  definition-of-done.md
  project-readback.md    the verbatim read-back, and what came back different
  output-contract.md     the shape, written before the output
  skill/                 the Skill, and the reuse check
  analysis/              the session, the claim table, the tagged finding
  chain/                 what it does, prediction.md, what happened
  sessions/              the working behind all of it
```

`README.md` is the front door. Write it as though it is the only file read carefully.

## How it is graded

**Component** | **Share**
--------------|----------
The tracked deliverable, and whether the tracking is real | 25%
The critique: claim types, evidence, verdicts | 30%
The finding: what it claims, and where it stops | 20%
The chain, its prediction, and the comparison | 25%

Process evidence is not a separate line. It is assessed inside every component, because a
component with no visible working cannot be assessed on its reasoning at all.

The three requirements are assessed the same way: the read-back inside Part 2, the output
contract inside Part 2, the Skill inside whichever part you used it in.

## How a project differs from a module

This is the first project in this course, so the distinction has not come up yet. It is worth
being explicit, because it changes how you should work.

| A module | A project |
|---|---|
| The work is handed to you, in acts, in order | You choose the subject and decide what the work is |
| One week, one session, prescribed steps | Two weeks, no session in between, and you set the steps |
| Checks tell you exactly what is being looked at | Components tell you what is weighted; how you get there is yours |
| Finishing means the acts are done | Finishing means you decided what done was, wrote it down, and met it |

The practical consequence: nobody is going to tell you you are behind. That is what Part 1's
tracking is actually for, and it is why it is worth 25% of a project that is mostly about
analysis.

## The standard, stated plainly

This project is not asking you to produce a correct answer. It is asking you to produce work
where **someone else can tell how much to trust each part of it**, including the parts you were
unsure about.

That is a higher bar than being right, and it is the one that transfers.
