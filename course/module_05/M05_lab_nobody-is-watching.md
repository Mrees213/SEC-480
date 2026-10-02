<h3 align="center">SEC 480: Advanced AI Practicum</h3>

# When it fails and nobody is watching

**Assigned:** Friday 2 October.
**Due:** Thursday 8 October, 9:00 pm Eastern. One week, the same as every module.

## The situation

Last module you set something running and walked away. One task, one run, one result you came
back and read.

This week the service desk hands you a queue. Six tickets, exported Tuesday afternoon, in
`course/module_05/M05_queue/`. They arrive the way tickets actually arrive: written by six
different people in six different moods, and the titles are not reliable.

The instruction has not changed since module 4. **Make it not need you.**

### Where module 4 left you

At the end of module 4 you wrote `handover.md`. Two answers in it matter this week:

* **Question 2, what it relies on being true.** Each item is a place the work can go wrong
  without telling you.
* **Question 3, how somebody would know it had stopped working.** Your answer was a prediction.
  Nobody tested it.

This module tests it. Acts 1 and 2 give you more work and a second task to run. Act 3 breaks one
of the things you said it relies on, and you find out whether your answer to question 3 was true.
Act 4 fixes what the first three found. Keep `handover.md` open in another tab.

In this lab, **the procedure** means your Skill, the one you built in Project 1 and carried
through module 4.

## What this module is really about

Module 4 asked whether you could get something running. This one asks a harder question, and it
is the one the unit is built on:

> **How would you know if it had stopped doing the job, while continuing to report that it had?**

Not "did it crash". A crash is a gift. A crash tells you. The thing you are practising against
this week is the run that finishes, returns something that looks like an answer, and is wrong or
empty for a reason nothing on the screen mentions.

| | Module 4 | Module 5 |
|---|---|---|
| Inputs | One, chosen by you | Six, chosen by other people, uneven on purpose |
| Runs | Once | Repeatedly, on a schedule |
| The failure you are looking for | Did it run | Did it run and quietly do nothing |

## How this lab works

**Four acts. An act is one of the numbered sections below**, and each one states what it is
worth and how you know it worked. They run in order because each one leaves the next one
something to work on:

| Act | The question it asks | What it hands the next act |
|---|---|---|
| 1. Work the queue | Where does your procedure fail on other people's input? | Six results, some of them wrong |
| 2. The thing that runs every day | What can a routine report not tell you? | A second task, and a habit of checking where it reads from |
| 3. Break it on purpose | Would you notice a quiet failure? | A broken run that looked fine |
| 4. Teach it to stop | What does it do when it cannot proceed? | The fix, written from acts 1 to 3 |

**Fourteen checks are marked through the acts, CP1 to CP14.** Each names what it looks at and
what it is worth.

Everything you produce goes in `module_05/` on a branch. Act 1 sets that up.

**Everything graded here works in a browser.** No install, no administrator, no desktop
application required.

### Using an agent

You may hand any part of this lab to an agent. You own what comes back. When an agent wrote most
of a file, put `operator-notes.md` in `module_05/`, in your own words:

1. **What you asked.** The prompt or prompts, pasted.
2. **What you checked, and how.** At least two claims you checked against a source, with the
   command or file you used.
3. **What you changed or rejected.** At least one thing the agent got wrong or you overrode, and
   why.
4. **What you would not trust.** The part you would check again before relying on it.

Without these notes, the checks that ask for your judgment or your own words earn partial credit.
Your journal is always yours: an agent does not write it.

### If module 4 did not leave you with something running

If your account does not show a scheduling control, or you are joining this from behind, that is covered.
**Every act below has a by-hand route and it is worth the same marks.** Where the lab says a
scheduled run, you run the same instructions yourself at two separate sittings and write down
when each one was. Nothing here is graded on owning a feature.

Say which route you took, once, at the top of `module_05/notes.md`, on a line of its own in
exactly this shape:

```
Route: scheduled
```

The permitted values are exactly `scheduled` and `by-hand`. No other value.

---

## Act 1: work the queue (4 points)

Read `queue.md` first, then the six tickets.

Your Skill from Project 1, the one you carried into module 4, is the procedure. Point it at each ticket in turn, one at
a time, and let it do what it does. Do not fix the tickets first. Do not rewrite the procedure
yet. Act 4 is where that happens, and it will be worth more to you once you have seen what
actually breaks.

### Set up first

```bash
git switch -c module_05
mkdir -p module_05
```

Through the connector, an issue in GitHub for each act, four of them, each with a title, a
sentence saying what it covers, you as the owner, and a date you believe. Attach each one to
`Milestone_02`, which is already in your repository and is dated 22 October.

### Then run all six

Write the outcome of each into `module_05/queue-results.md`, as a table in exactly this shape:

| Ticket | Outcome | Owner | One line |
|---|---|---|---|
| SD-4691 | `handled` | `agent` | what it concluded |

The `Outcome` column takes exactly one of three values and no others:

* `handled`: the procedure did what it was built to do and produced something you would send on.
* `refused`: the procedure stopped and said it could not proceed. This is a good outcome.
* `wrong`: the procedure produced an answer, and the answer is not right, or is right about
  something nobody asked.

The `Owner` column is your call, not the procedure's: who should handle this ticket from now
on. It takes exactly one of two values:

* `agent`: the procedure can be trusted with this kind of ticket without you.
* `person`: a person should handle it, because the agent lacks something a person has.

**Six rows. Every ticket gets one, including the ones that go nowhere.**

> **CP1 (1 point).** Four issues in GitHub, each with an owner and a date, attached to
> `Milestone_02`, created before the first commit of real work. The commit history shows this,
> so do not backfill it.
>
> **CP2 (1 point).** All six tickets were run through the procedure, and `queue-results.md` has
> six rows.
>
> **CP3 (1 point).** Every `Outcome` cell holds exactly one of `handled`, `refused`, `wrong`,
> and every `Owner` cell holds exactly one of `agent`, `person`.
>
> **CP4 (1 point).** For each row that is not `handled`, and for each row whose `Owner` is
> `person`, one sentence on what the procedure needed and did not have.

**You know it worked when** `queue-results.md` has six rows and at least one of them is not
`handled`. If all six came back `handled`, read them again. This queue was built so that some
of them cannot be.

**Produces:** `module_05/queue-results.md`, `module_05/notes.md` with its `Route:` line, four
issues in GitHub, and a branch.

---

## Act 2: the thing that runs every day (3 points)

The queue is work that arrives and varies. This act is the opposite kind, and it fails
differently.

Build a second scheduled task: **a morning recap of what you owe and when.** It reads a snapshot
of your own issues and your milestone, and writes a short digest. What is open, what is due, what
is closest.

A scheduled task cannot read your issues in GitHub directly. So the work is split between two
machines, and each does the part it can:

1. **GitHub takes the snapshot.** Copy `course/module_05/M05_status/status.yml` into your
   repository at exactly `.github/workflows/status.yml`. In GitHub: **Add file**, **Create new
   file**, type that path, paste the file, and commit to `main`. Every morning GitHub writes your
   issues to `status/issues.json` and the time it looked to `status/taken-at.txt`.
2. **Run it once now.** Your repository's **Actions** tab, **status snapshot**, **Run workflow**.
   When it finishes, `status/issues.json` is in your repository. If it is not, the run shows red
   and says why.
3. **Your Project reads the snapshot.** In your Project, find the **Context** box, click its
   **+**, choose **GitHub**, pick your repository, tick the `status` folder so both files are
   selected, and choose **Add files**. Use the **Context** box, not the GitHub option beside the
   chat box: that one only links a repository to a single chat, and a scheduled task cannot see
   it. The Project keeps the copy it last synced and does not refresh by itself: once the
   Action has run again, a recap can find nothing at all to read. Click the **Sync** icon on
   the repository card after each Action run, and before any recap run you want to count.
4. **Claude writes the recap.** The scheduled task reads `status/issues.json` and
   `status/taken-at.txt` from the Project, never GitHub itself. Ask it to say how many issues it
   read, and check that number against your repository.

> **Do not skip the Sync.** The Project keeps its own copy of `status/`, and it does not update
> when the Action runs. Every time the Action runs, click **Sync** on the repository card in your
> Project's **Context** box. With no Sync the recap has nothing current to read, and the run
> fails with `READ FAILED`.

Schedule the recap daily. Bind it to the same Project. Then leave it alone and let it run at
least twice.

Choose **Daily** under Frequency. A task that repeats keeps running until you stop it: when you
have your two runs, open **Scheduled** in the sidebar and switch its toggle to **Paused**.

### The part that is actually being marked

A recap that runs every morning is read carefully on day one and skimmed by day three. That is
not a character flaw, it is what routine does to attention, and it is why this act exists in a
module about noticing.

So: **what can your recap not tell you?** Go and look at where it gets its information before
you answer. One thing in particular is worth finding on your own, and you will find it by
comparing your digest against the lab you are reading now.

Write the digests and your answer into `module_05/recap.md`: what you scheduled, the output
from at least two separate runs with the date of each, and what the recap cannot tell you.

> **CP5 (1 point).** `.github/workflows/status.yml` is in your repository and has run at least
> once, the `status/` files are in the Project's **Context** box, and a daily recap task exists,
> bound to the Project, reading `status/issues.json`.
>
> **CP6 (1 point).** `recap.md` carries the output of at least two runs, each with the date it
> ran. By hand is worth the same, at two separate sittings.
>
> **CP7 (1 point).** `recap.md` names at least one thing the recap cannot tell you, traced to
> the source it reads rather than to the wording of your instructions.

**You know it worked when** you have two digests from two different days sitting in the same
file, and you can say what a reader of only those digests would not know.

**Produces:** `module_05/recap.md`, `.github/workflows/status.yml`, and a daily task.

---

## Act 3: break it on purpose (7 points)

The largest act in the unit, and the one this module is named after.

You are going to break your own procedure, deliberately, in a way you choose, and then let it
run without you and watch it report success.

### Predict first. This is not optional and it is worth the most.

**Before you break anything**, write `module_05/prediction.md` and commit it. It answers three
questions:

1. **What you are going to break, exactly.** Not "I will make it fail". Name the change: an
   instruction removed, a file it reads renamed, a required input left out, a step reordered.
2. **What you expect to see.** What comes back? An error? A short answer? The same answer as
   before? Be specific enough to be wrong.
3. **Where you expect to notice it.** In the output, in a log, in the digest from act 2, or not
   at all.

Commit that file before the break exists. The commit history is the evidence and it cannot be
backfilled.

### Then break it, and leave

**Choose the break from your own `handover.md`.** Question 2 lists what your work relies on. Pick
one of those and remove or damage it quietly. If you have no handover, pick something your
procedure reads rather than something it needs to start.

Make the change. Let the task run on its schedule, or by hand at a separate sitting. Do not
watch. Come back afterwards and read what it produced.

**Turn the broken version off once it has run.** It repeats otherwise, and a procedure you know
is broken is not one to leave running.

### Then compare

In `module_05/break.md`: what you actually saw, set against what you predicted, and the
difference between them.

**If you predicted an error and got a clean report, that is the module.** Write it plainly. Say
what in the output would have told you, if anything would have, and what you would have to check
to find out. If you predicted correctly, say what made you see it coming, because that is worth
as much.

> **CP8 (2 points).** `prediction.md` names the break, what is expected, and where it would be
> noticed, **committed before the break was made.**
>
> **CP9 (1 point).** `break.md` describes the change precisely enough that somebody else could
> make the same one.
>
> **CP10 (2 points).** The broken version ran without you watching, and `break.md` carries what
> came back and when.
>
> **CP11 (2 points).** `break.md` sets the result against the prediction and says what in the
> output would or would not have revealed the break.

**You know it worked when** you are holding an output produced by a procedure you know is
broken, and you can point at what in it does and does not give that away.

**Produces:** `module_05/prediction.md` and `module_05/break.md`.

---

## Act 4: teach it to stop (4 points)

Two acts ago the queue gave you tickets your procedure could not honestly handle. One act ago
you broke it yourself and it carried on.

Both have the same cause. **The procedure has no way of saying "I cannot do this."** It only
knows how to produce an answer, so when the ground disappears it produces one anyway.

Fix that. Before you do, reread your module 4 `handover.md`, question 3: how somebody would know it
had stopped. If act 3 showed that answer was wrong, that is one of your failure modes.

Rewrite your Skill so that it states, in its own words, what it does when it cannot proceed.
At a minimum it names:

* **What it requires before it starts.** If something is not there, it stops and says which
  thing.
* **What is out of scope.** Say what your procedure is not for, in its own words. You now have
  six worked examples of what turns up when nobody is filtering.
* **What it does when an input is incomplete.** Asking is a valid answer. Guessing is not.
* **How a refusal is worded**, so a refusal cannot be mistaken for an answer by somebody
  skimming.

Then run the two tickets that went worst through the rewritten version and show the difference.

Write it into `module_05/handling.md`: the failure modes you found, what the procedure now does
about each, and the before and after on those two tickets.

> **CP12 (1 point).** `handling.md` lists the failure modes found in acts 1 and 3, from your own
> results rather than from this list.
>
> **CP13 (2 points).** The Skill now states what it requires, what is out of scope, what it does
> with an incomplete input, and how a refusal is worded. The updated Skill is in your repository.
>
> **CP14 (1 point).** Two tickets re-run through the rewritten procedure, before and after both
> shown.

**You know it worked when** a ticket that used to come back with a confident wrong answer now
comes back saying what is missing.

**Produces:** `module_05/handling.md`, and an updated Skill.

---

## What is due

On the `module_05` branch, in a pull request.

**The pull request is a container and nobody opens it.** It is not reviewed, nobody is assigned
to it, and you are not waiting on anybody. Open it, describe what is in it, and you are finished.

- [ ] four issues in GitHub, created before the work, attached to `Milestone_02`
- [ ] `notes.md`, with a `Route:` line reading `scheduled` or `by-hand`
- [ ] `queue-results.md`, six rows, every outcome one of the three permitted values
- [ ] a daily recap task, and `recap.md` with two runs dated and what the recap cannot tell you
- [ ] `prediction.md`, committed before the break existed
- [ ] `break.md`, the result set against the prediction
- [ ] `handling.md`, and the rewritten Skill in your repository

Alongside each of those, the working that produced it. `course/showing-your-work.md` covers what
that means. A correct file with no visible working does not get full credit, and a wrong file
with clear reasoning does not lose it all.

**The journal is a separate deliverable**, worth 6 points on its own, due at the same time. It is
in `M05_brief_journal.md`.

## When it does not work

**You have nothing running from module 4.** Take the by-hand route, say so in `notes.md`, and
lose nothing. Every check is written to be earnable either way.

**Your procedure handled all six tickets cleanly.** Read the results rather than the outcomes.
For each one, ask what the procedure was working from and whether the ticket actually contained
it. A confident answer built on something nobody supplied is a `wrong`, not a `handled`.

**You think two tickets are the same incident.** Deciding that is your call. Say which ones and
why, either way. The reasoning is what is marked, not the decision.

**The recap fails with `READ FAILED`, or reads old data.** Click **Sync** on the repository card in
the Project's Context box, then run it again. Write down that it happened, since a recap running
on a stale copy looks just like one running on a current copy.

**The recap comes back empty.** Write that down and keep it. An empty digest and a digest that
could not read anything look identical, and act 2 is asking you to notice exactly that.

**You broke it and it failed loudly.** Then it was the wrong break for this act. Say what
happened, keep it, and break something quieter: something it reads rather than something it
needs.

**You cannot tell whether an outcome is `wrong` or `refused`.** If it produced an answer, it is
not a refusal, however hedged the answer was. That distinction is the point of the column.

**Something else.** Add a `help.me` file to your repository describing where you are stuck, and
push it. A response comes back in your repository, usually within a few hours, and it works even
when nothing else does.
