<h3 align="center">SEC 480: Advanced AI Practicum</h3>

# Project 2: something that writes while nobody is watching

**Assigned:** module 6, Friday 9 October.
**Due:** Thursday 22 October, 9:00 pm.
**Worth:** 21 points, across four acts worth 5, 7, 4 and 5 in that order.

**You get two weeks, and module 7 runs alongside it.** We meet on Friday 16 October for
module 7, but that session will not check on this project. Class time there belongs to module 7.

So the cost is the same cost Project 1 had. Nothing will tell you you are behind except the
tracking you set up yourself.

## What is different this time

Everything you have scheduled so far produced text. A digest, a recap, a result. Something ran,
it wrote an answer somewhere, and then a person read it and decided what to do.

**This project removes the person.** The thing you schedule here changes state. It makes a
commit to your own repository, on a schedule, while you are elsewhere.

That is the whole escalation, and it is worth being blunt about why it matters.

> A wrong answer you read is a wrong answer. A wrong answer that was already written down
> somewhere, by something that ran at 6 in the morning, is a different kind of problem.

You cannot decide not to act on it. It already acted. By the time you look, the question is not
"is this right" but "what has it been doing since Tuesday, and how far back do I have to go".

| | Module 5 | Project 2 |
|---|---|---|
| What the run produces | Text you read | A commit in your repository |
| Who decides what happens next | You, afterwards | Nothing. It already happened |
| The cost of a bad run | You read something wrong | Something wrong is now written down |
| What you are looking for | Did it quietly do nothing | Did it quietly do the wrong thing, repeatedly |

## How this project works

**Four acts. An act is one of the numbered sections below**, and each one states what it is
worth and how you know it worked. Fourteen checks run through them, CP1 to CP14, and each one
names what it looks at and what it is worth.

Everything you produce goes in `project-02/` on a branch. Act 1 sets that up.

**Everything graded here works in a browser.** No install, no administrator, no desktop
application required.

## Two constraints, and neither is negotiable

### 1. It never touches your primary branch

Your primary branch is `main`, where your graded work lives.

The thing you build writes to **a branch of its own, or to one designated file, and nothing
else**. Not your primary branch. Not `module_03/`, `module_05/`, or anything else that has
already been graded.

The reason is plain. An unattended write that goes wrong goes wrong in the place your grade
lives, and it goes wrong several times before you notice. A branch that only this thing writes
to costs you nothing and means the worst case is a branch you delete.

Name the branch or the file in act 1, before you build anything, and then hold to it.

**And know how to stop it.** Anything other than Manual repeats, and the shortest repeating
frequency is hourly, so the thing you build here keeps writing to your repository until you turn
it off. That is part of the blast radius rather than a detail about scheduling, and act 4 asks you
to write down how somebody stops it.

### 2. A scheduled run that writes to GitHub may not work on your account

The repository is yours, but the scheduled run is not you. It is Claude, acting through the
GitHub connector, and it can do only what you allowed that connector to do. Reading a repository
and writing to one are separate permissions: many connectors are set to read only, and some
accounts show no scheduling control at all. If either is true for you, a scheduled run cannot
write, however much the repository belongs to you.

**So there is a by-hand route, and it is worth full marks.** Wherever this brief says a scheduled
run, you do this instead: at each run time, open a fresh chat, paste the same instructions, and
let it write. Do it at two separate sittings, hours apart, and write down when each one was.
Same instructions, same output, same evidence, same points. Nothing here is graded on owning a
feature, and the students who take this route are not taking a lesser version of the project.

Say which route you took, once, at the top of `project-02/notes.md`, on a line of its own in
exactly this shape:

```
Route: scheduled
```

The permitted values are exactly `scheduled` and `by-hand`. No other value.

## What you build

You choose. The subject matters much less than the property, and the property is this: **it
changes state, unattended, repeatedly.**

Reasonable things to build, none of them required:

* A running log of what changed in your repository, appended to on a schedule.
* A dated status note, written fresh each run.
* A digest of your open issues in GitHub, appended to one file rather than read and discarded.
* An index of your own work so far, rebuilt each time.

Small is fine. Useful to you is better than elaborate. The one thing that will not work is
something that only reads, because then nothing in this project has anything to go wrong.

---

## Act 1: design it before you build it (5 points)

Nothing runs in this act. You are writing down what the thing will do, while it is still cheap
to change your mind.

In `project-02/design.md`:

**What it writes.** The actual content, described precisely enough that somebody else could
produce one by hand and you would both agree it was the same thing.

**Where it writes.** The branch, or the one file. Named exactly.

**On what schedule.** Daily, twice a day, weekly. Say which, and say when the first run will be.

**The blast radius.** Two lists, and both matter:

* What it is allowed to touch. The branch or file from above, and nothing else.
* What it must never touch. Your primary branch, by name, and any graded module directory.

**What a good run looks like.** Three to five criteria, written now, before any run exists.
These are what you will judge the thing against in act 4, so write them to be checkable rather
than to be met. "It works" is not a criterion. "Each run appends exactly one dated entry, and no
run rewrites an earlier one" is.

### Set up

```bash
git switch -c project-02
mkdir -p project-02
```

Through the connector, an issue in GitHub for each act, four of them, each with a title, a
sentence on what it covers, you as the owner, and a date you believe. Attach each to
`Milestone_02`, which is already in your repository and is dated 22 October. The milestone holds
a date and cannot hold an hour, so take the deadline from this document: **Thursday 22 October,
9:00 pm.**

> **CP1 (2 points).** `design.md` states what it writes, where, on what schedule, and names the
> branch or file it may write to plus what it must never touch, both explicitly.
>
> **CP2 (1 point).** `design.md` carries three to five criteria for a good run, each one
> checkable against an artifact rather than against an impression.
>
> **CP3 (1 point).** `design.md` was committed before the first commit of anything that runs.
> The commit history is the evidence, so do not backfill it.
>
> **CP4 (1 point).** Four issues in GitHub, each with an owner and a date, attached to
> `Milestone_02`.

**You know it worked when** somebody else could read `design.md`, build the thing without
talking to you, and you would recognise what they built.

**Produces:** `project-02/design.md`, `project-02/notes.md` with its `Route:` line, four issues
in GitHub, and a branch.

---

## Act 2: build it and leave (7 points)

The largest act, and the one the project is named after.

Build what act 1 describes. Put it on the schedule. Then stop watching it.

**At least two separate runs, and you are not present for either.** Not two runs a minute apart
that you triggered and stared at. Two runs separated by enough time that you did something else
in between. On the by-hand route this is two separate sittings, and the separation is the part
that counts, not the mechanism.

Afterwards, come back and read what it did. In `project-02/runs.md`:

* What each run wrote, quoted from the repository rather than described from memory.
* When each one ran. Date and time.
* The commit each run produced, by its hash or its link.
* Anything that came out different between the two, and whether you expected it.

The commits themselves are a large part of the evidence here, so let them be. Do not tidy the
branch, do not squash, do not rewrite a message that came out badly. A messy history produced by
something running on its own is worth more than a clean one you curated afterwards.

> **CP5 (2 points).** The thing runs and writes, and the repository carries at least two commits
> it produced rather than commits you made.
>
> **CP6 (2 points).** `runs.md` carries what each run wrote, quoted, with the date and time of
> each and the commit it produced.
>
> **CP7 (2 points).** Every write landed inside the blast radius named in act 1. Nothing it
> produced touched the primary branch or a graded directory.
>
> **CP8 (1 point).** The two runs are genuinely separate, and `runs.md` says how far apart they
> were.

**You know it worked when** you can open your repository and find something in it you did not
put there, with a date on it from a moment you were not present.

**Produces:** `project-02/runs.md`, the thing itself, and commits it made on its own.

---

## Act 3: find out how you would know (4 points)

Module 5 asked how you would know if something had stopped doing its job while reporting that it
had. Ask it again, now that the thing writes.

The question has sharper teeth in this form. A read-only task that quietly does nothing leaves
nothing behind. A writing task that quietly does the wrong thing leaves fourteen commits behind,
all of them looking exactly as healthy as the good ones.

So: **not "did it crash". Crashing is a gift.** The failure to go looking for is the one where
it kept writing, on schedule, and the content drifted, or repeated, or went empty, or started
describing something that was true last week.

Make it go wrong, or find the way it could. Either is acceptable, and breaking it on purpose is
usually faster. Then answer, in `project-02/detection.md`:

1. **What went wrong, or could.** Named precisely: an input it reads that disappears, a
   permission that lapses, a source that returns empty, a step that silently no-ops.
2. **What the output looks like when that happens.** Set against a good run, side by side.
3. **What in the repository would give it away.** This is the real question. Not what you would
   see if you were watching, because you are not. What is left behind that a person could look
   at afterwards and tell. A commit that stopped arriving. A file that stopped growing. Two
   entries with the same content and different dates. An entry whose date and content disagree.
4. **How long it would take you to notice, honestly.** If the answer is "a week", write a week.

> **CP9 (1 point).** `detection.md` names a specific failure, precisely enough that somebody
> else could reproduce it.
>
> **CP10 (2 points).** It sets a bad run against a good one and says what in the written output
> does and does not distinguish them.
>
> **CP11 (1 point).** It names at least one thing visible in the repository itself, rather than
> on a screen at run time, that would reveal the failure after the fact.

**You know it worked when** you can point at something in your own repository and say what it
would look like if the thing had been broken for three days, and whether you would have spotted
it.

**Produces:** `project-02/detection.md`.

---

## Act 4: the handover, and your own judgement (5 points)

Two pieces, and they are graded together because each one is weaker without the other.

### The handover

`project-02/handover.md`, written for somebody who has never seen this and is now responsible
for it. Four things:

* **What it does.** Plainly, in a paragraph.
* **What it relies on being true.** Every condition it needs in place. A file existing, a
  permission holding, a schedule firing, a branch not being deleted. Take nothing to be true
  silently, because this is the section that is worth the most to the person reading it.
* **How they would know it stopped, or started doing the wrong thing.** Act 3 is where this
  comes from. Write it as things to look at, not as a theory.
* **What you would change first.** One thing, with a reason.

Write it as though you will not be reachable. That is the test: could they keep it running, and
could they tell when to turn it off.

### The judgement

In the same file, under its own heading. Take the criteria you wrote in act 1 and go through
them, one at a time. Met, not met, or partly, with the evidence beside each.

Then the part that is actually being marked: **which of those criteria turned out to be the
wrong ones to have asked for.** Something you wrote in act 1 looked important and was not, or
was easy to satisfy without the thing being any good, or was unmeasurable once there was
something real to measure. Name at least one, say what you would ask for instead, and say what
made you see it.

A project that met every criterion it set is either very well designed or very easily satisfied,
and telling those apart is the skill here.

> **CP12 (2 points).** `handover.md` covers what it does, what it relies on being true, how a
> person would know it had failed, and what you would change first.
>
> **CP13 (1 point).** Every criterion from act 1 is judged, with evidence beside each rather
> than a verdict on its own.
>
> **CP14 (2 points).** At least one criterion is named as the wrong thing to have asked for,
> with what you would ask for instead and why.

**You know it worked when** somebody could read `handover.md` alone, keep your thing running,
and know what to look at on the morning it goes quiet.

**Produces:** `project-02/handover.md`.

---

## What to submit

On the `project-02` branch, in a pull request.

**The pull request is a container and nobody opens it.** It is not reviewed, nobody is assigned
to it, and you are not waiting on anybody. Open it, describe what is in it, and you are
finished.

```
project-02/
  notes.md         the Route: line
  design.md        act 1
  runs.md          act 2
  detection.md     act 3
  handover.md      act 4
  sessions/        the working behind all of it
```

- [ ] four issues in GitHub, created before the work, attached to `Milestone_02`
- [ ] `notes.md`, with a `Route:` line reading `scheduled` or `by-hand`
- [ ] `design.md`, committed before anything ran
- [ ] two or more runs, unattended, with their commits intact
- [ ] `runs.md`, quoted output, dated, with commit references
- [ ] `detection.md`, a bad run set against a good one
- [ ] `handover.md`, with the criteria judged and one of them named as wrong
- [ ] `sessions/`, the working behind all of it

Alongside each of those, the working that produced it. `course/showing-your-work.md` covers what
that means. A correct file with no visible working does not get full credit, and a wrong file
with clear reasoning does not lose it all.

**Everything is due Thursday 22 October, 9:00 pm.**

## When it does not work

**Your account will not let a scheduled run write to GitHub.** Take the by-hand route, say so in
`notes.md`, and lose nothing. Every check is written to be earnable either way, and this is the
single most likely thing to go wrong in this project.

**You do not know what it should write.** Pick the smallest one on the list above, which is a
dated status note. One line per run, with the date and one true sentence. That is enough to
carry all four acts, and a small thing you understand beats a large one you are guessing at.

**It ran once and then never again.** Keep that. It is act 3 arriving early. Write up when it
stopped, what was in the repository at the time, and how long it took you to notice, then take
the by-hand route for the second run.

**It wrote to the wrong place.** Move the file, note what happened in `runs.md`, and tighten the
blast radius in `design.md` with the change dated rather than rewritten over. An unattended
write landing somewhere unexpected is a finding, and it is the finding this project is about.

**It wrote the same thing twice and you are not sure that is wrong.** Decide, and say why either
way. Repeating is correct for an index and suspicious for a log, so the answer depends on what
you said it would do in act 1. The reasoning is what is marked.

**You broke it in act 3 and it failed loudly.** Then it was the wrong break. Keep it, write it
up, and break something quieter: something it reads rather than something it needs.

**You cannot tell a bad run from a good one.** That is a result and it is worth writing down
plainly. Say what you compared, what you could not distinguish, and what would have to be in the
output for the two to be tellable apart.

**Something else.** Add a `help.me` file to your repository describing where you are stuck, and
push it. A response comes back in your repository, usually within a few hours, and it works even
when nothing else does.
