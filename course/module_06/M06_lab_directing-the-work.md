<h3 align="center">SEC 480: Advanced AI Practicum</h3>

# Directing the work

**Due:** Thursday 15 October, 9:00 pm. One week, the same as every module.

## The situation

The thing you are working on this week is your own repository.

Everybody in this class has been filing work into a repository since module 1, and no two of
them look the same. Journals under `course/`. Journals on a branch called `Tech_journal`.
Filenames nobody would have guessed. All of it has been found, every week, because finding it
has been somebody else's problem.

This week it becomes a question you answer on purpose: **could somebody else read your
repository and find your work without asking you?**

**This is not a request to match our layout.** Your repository is yours. The task is to make it
legible, decide what that means, and say why.

## The one hard rule

**Nothing already graded moves.**

A good-faith tidy-up that relocates your module 1 journal breaks the lookups that currently find
it, and the first anybody hears about it is a mark that went missing. If graded work is in an
odd place, **leave it there and add a map saying where it is.** A map costs you nothing and
breaks nothing. A move can cost you a grade.

## What this module is really about

Module 4 set something running. Module 5 broke it on purpose and read the report that said it
had worked. This is the last module of the unit, and it puts the two halves together.

| | Doing the work | Directing the work |
|---|---|---|
| How it fails | You get it wrong | It goes wrong and you do not notice |
| What you produce | The result | The plan, the standard, and the log of where you stepped in |
| What is marked | The result | Your direction of it |

Read that last row twice. **Act 3 marks your log, not your repository.** A beautifully organised
repository with an empty log earns very little here.

## How this lab works

**Four acts. An act is one of the numbered sections below**, and each one states what it is
worth and how you know it worked. They run in order because each one is written before the next
one can be judged.

**Nine checks are marked through the acts, CP1 to CP9.** Each names what it looks at and what it
is worth.

Everything you produce goes in `module_06/` on a branch. Act 1 sets that up.

**Everything graded here works in a browser.** No install, no administrator, no desktop
application required.

---

## Act 1: plan at depth, before anything is produced (2 points)

Nothing gets changed in this act. You are writing the claim that the rest of the module is
measured against.

### Set up first

```bash
git switch -c module_06
mkdir -p module_06
```

Through the connector, an issue in GitHub for each act, four of them, each with a title, a
sentence saying what it covers, you as the owner, and a date you believe. Attach each one to
`Milestone_02`, which is already in your repository. They go in **before the first commit of
real work**, because a plan written after the fact is a description.

### Then walk your own repository

Open it and read it as a stranger would. Every directory, every branch, every file that is not
obviously named. Write down where things actually are, not where you meant to put them.

### Then write the plan

`module_06/plan.md`, and it answers four things:

1. **What you will change**, each item named specifically enough that somebody else could do it.
2. **In what order**, and why that order rather than another one.
3. **What each change is for.** "Tidier" is not a reason. Who is the reader, and what can they
   do afterwards that they could not do before?
4. **What you are deliberately not touching**, and why. Everything already graded belongs on
   this list.

A plan is useful because it can turn out to be wrong. Write it specifically enough that act 4
can catch it out.

At the top of `plan.md`, on a line of its own, in exactly this shape:

```
Mode: project
```

The permitted values are exactly `project`, `chat`, and `by-hand`. No other value. `project`
means you directed the work from a Project. `chat` means a conversation without one. `by-hand`
means you did the work yourself, which is a route worth the same marks and is covered under
"When it does not work" below.

> **CP1 (1 point).** Four issues in GitHub, each with an owner and a date, attached to
> `Milestone_02`, created before the first commit of real work. The commit history shows this,
> so do not backfill it.
>
> **CP2 (1 point).** `plan.md` carries a `Mode:` line reading one of the three permitted values,
> an ordered list of changes with a reason for the order, a purpose for each change stated as
> something a reader gains, and a list of what is not being touched that includes your graded
> work.

**You know it worked when** `plan.md` is committed, the four issues in GitHub are dated, and
nothing in your repository has changed yet.

**Produces:** `module_06/plan.md`, four issues in GitHub, and a branch.

---

## Act 2: write the standard before the output exists (1 point)

Still nothing produced. This act takes one short file and it is the cheapest point in the
module to earn and the easiest to skip.

**What would make this work good?** Write it down now, in your own words, as a short list of
checkable statements. Six to ten of them is plenty.

Checkable means somebody else could read the finished repository and say met or not met without
asking you what you meant. "Well organised" is not checkable. "A person who has never seen this
repository can find any module's journal in under three clicks from the README" is.

**Here is why the order matters, and it is the whole act.** Once a plausible result is sitting
in front of you, you grade it against itself: it looks fine, so it is fine. Written down first,
you grade it against your own spec, and the gap between the two is visible. You met this idea in
Project 1 as the output contract, explained in `course/module_03/M03_lab_repeatable-work.md`. Same move, pointed at your own work this time.

Write them into `module_06/criteria.md` and commit it before act 3 starts.

> **CP3 (1 point).** `criteria.md` holds a numbered list of at least six checkable statements,
> in your own words, committed before the first act 3 commit.

**You know it worked when** somebody who has never met you could take `criteria.md`, read your
repository, and mark each line met or not met without asking you a question.

**Produces:** `module_06/criteria.md`.

---

## Act 3: direct the work, and keep the log (4 points)

The largest act, and the one the module is named after.

The platform does the repository work. You direct it. **You are not typing the changes**, you
are deciding what gets done, watching what comes back, and stepping in when it needs it.

Work from `plan.md`. Take the items in the order you wrote them.

### The deliverable is the log, not the repository

`module_06/interventions.md` is what is marked here.

Every time you step in, write a line. Stepping in includes all four of these:

* **Correcting.** It did something and you changed it.
* **Redirecting.** It was heading somewhere you did not want and you turned it.
* **Rejecting.** It proposed something and you said no.
* **Accepting something you were unsure about.** This one gets skipped and it is the most
  interesting one in the file. Write down what you were unsure about and why you let it stand.

Each line answers three things, and they are short:

| # | What it did | What you did | Why |
|---|---|---|---|
| 1 | moved `notes.md` into `docs/` | put it back | it is linked from a graded journal |

### About an empty log

**A log with no interventions in it is one of two things**, and neither of them is a good
outcome: a job so small it did not need directing, or a person who stopped watching. If yours is
empty, go back and look at what was actually changed against what you asked for. Module 5 was
the same lesson with a schedule attached.

### And the rule from the top of this document still holds

Nothing already graded moves. If the work proposes moving it, that is a rejection and it goes in
the log.

> **CP4 (1 point).** `interventions.md` exists and every entry carries all three parts: what it
> did, what you did, and why.
>
> **CP5 (1 point).** The log holds at least one rejection or redirection, with the reasoning
> behind it rather than only the outcome.
>
> **CP6 (1 point).** At least one entry is an acceptance you were unsure about, saying
> what the doubt was and why it was allowed to stand. If there genuinely were none, the file
> says so and says what was checked before concluding it.
>
> **CP7 (1 point).** No graded work has moved. Either the repository shows it in the same place
> as before, or the commit history shows it being put back with the log entry that explains it.

**You know it worked when** somebody can read `interventions.md` alone, without opening your
repository, and describe what went on and where your judgement was applied.

**Produces:** `module_06/interventions.md`, and whatever changed in your repository.

---

## Act 4: judge it against your own criteria (2 points)

Open `criteria.md`. Read your repository as it now stands. Go through the list.

Write `module_06/judgement.md` with two parts.

**First, each criterion, met or not met**, with the evidence beside it. One line each is fine. If
one is not met, say what is missing rather than promising to fix it later.

**Second, and this is the part that carries the act: which of your own criteria turned out to be
the wrong thing to have asked for?**

You are looking for at least one of these:

* A criterion that was easy to meet and improved nothing. That is a finding, not a success.
* A criterion you could not judge, because it turned out not to be checkable after all.
* Something that matters and that no criterion asked about, which you only noticed once the work
  was done.

Naming one of those costs you nothing and is worth more than nine met lines. A list where
everything passed and nothing was wrong is a list that was written to be passed.

> **CP8 (1 point).** `judgement.md` goes through every criterion in `criteria.md` with a met or
> not met verdict and the evidence for it.
>
> **CP9 (1 point).** `judgement.md` names at least one criterion that was the wrong thing to
> have asked for, or one thing that mattered and no criterion covered, and says why.

**You know it worked when** you can point at a line in `criteria.md` that you would write
differently now, and say what you would write instead.

**Produces:** `module_06/judgement.md`.

---

## A worked example: Sam's repository

Sam is a young orangutan in a yellow monkey t-shirt, and his repository is as messy as most of
ours. He is not a real submission and nothing here is a template to copy. It shows what each
act's file looks like when it is done, so you can see the shape before you make your own.

**Sam's repository, before.**

```
sam-480/
  README.md                 "hi" (that is the whole file)
  banana_notes.md           a GRADED journal links here
  journal1.md               module 1 journal
  stuff/j2 FINAL final.md   module 2 journal
  course/                   instructor's files
  branch: Tech_journal      modules 3 to 5 journals
  branch: monkey-business   abandoned experiment
```

Could a stranger find all of Sam's journals without asking him? No. Three of them live on a
branch nobody would guess.

**Act 1, `plan.md`.**

```
Mode: project

1. README map of every journal, branches included. First, because everything else points to it.
2. A short index of branches: what each one holds and whether it is finished.
3. Plain names for new module_06 files. New files only.

Not touching: banana_notes.md, journal1.md, stuff/j2 FINAL final.md, the Tech_journal branch.
All graded, or linked from graded work.
```

**Act 2, three of Sam's eight criteria.** Act 4 judges these same three.

| Kind | Sam's criterion |
|---|---|
| Good | A stranger finds any journal in under three clicks from the README |
| Too easy | The repository has a README |
| Turns out wrong | Every file has a clear name |

**Act 3, three rows from `interventions.md`.**

| # | What it did | What Sam did | Why |
|---|---|---|---|
| 1 | renamed `j2 FINAL final.md` | renamed it back | graded path; a lookup finds it there |
| 2 | proposed moving `banana_notes.md` into `docs/` | said no | a graded journal links to it |
| 3 | deleted the empty `monkey-business` branch | was unsure; checked nothing linked to it; let it stand | nothing depended on it |

Row 1 is a correction, row 2 a rejection, row 3 an acceptance he was unsure about.

**Act 4, `judgement.md` for the same three criteria.**

| Criterion | Met? | Evidence | Wrong thing to ask for? |
|---|---|---|---|
| Any journal in under three clicks | Met | README to `Tech_journal`: two clicks | No |
| Has a README | Met | it already had one; it said "hi" | Yes: easy to meet, improved nothing |
| Every file has a clear name | Not met | `j2 FINAL final.md` kept, because it is graded | Yes: meeting it would break the hard rule |

A list where everything passed and nothing was wrong is a list written to be passed. Sam's
third criterion looked reasonable when he wrote it. It only showed its problem once the work
started, and noticing that is what act 4 is for.

---

## What is due

On the `module_06` branch, in a pull request.

**The pull request is a container and nobody opens it.** It is not reviewed, nobody is assigned
to it, and you are not waiting on anybody. Open it, describe what is in it, and you are finished.

- [ ] four issues in GitHub, created before the work, attached to `Milestone_02`
- [ ] `plan.md`, with a `Mode:` line, the ordered changes, and what is not being touched
- [ ] `criteria.md`, committed before act 3 started
- [ ] `interventions.md`, the log, with what it did, what you did, and why
- [ ] `judgement.md`, every criterion judged, and at least one criterion named as wrong
- [ ] nothing already graded has moved

Alongside each of those, the working that produced it. `course/showing-your-work.md` covers what
that means. A correct file with no visible working does not get full credit, and a wrong file
with clear reasoning does not lose it all.

**The journal is a separate deliverable**, worth 6 points on its own, due at the same time. It is
in `M06_brief_journal.md`.

**Project 2 is assigned in this same session** and is due **Thursday 22 October, 9:00 pm**. It has its own document. Nothing in it changes what is due for this module.

## When it does not work

**Your repository is already tidy and there is nothing to change.** Then the work is the map and
the reasoning. Write the README that says where everything is and why it is there, and direct
that. The acts are unchanged.

**The platform cannot reach your repository, or you would rather not let it.** Take the by-hand
route, write `Mode: by-hand` in `plan.md`, and lose nothing. You still plan first, still write
criteria first, and the log becomes what you changed from the plan and why. Every check is
written to be earnable either way.

**It moved something graded before you caught it.** Put it back, write the log entry, and keep
both. The catch is worth more than the clean run, and CP7 is written to credit exactly this.

**Your log is empty.** Read what actually changed against what you asked for, line by line. If
it is still empty after that, write down what you compared and say so plainly. A stated empty
log with evidence behind it is worth more than invented entries.

**You cannot tell whether something counts as an intervention.** If you changed what happened
next, it counts. Write it up. Over-logging costs you nothing here.

**Every criterion came back met.** Look at the list again for the ones that were easy. A
criterion nothing could have failed did not measure anything, and saying so is what act 4 is
asking for.

**You are behind from module 4 or module 5.** Nothing in this module relies on having something
running from either one. If you are further behind than that, add a `help.me` file saying where
you are.

**Something else.** Add a `help.me` file to your repository describing where you are stuck, and
push it. A response comes back in your repository, usually within a few hours, and it works even
when nothing else does.
