<h3 align="center">SEC 480: Advanced AI Practicum</h3>

# The crossing point

**Due:** Thursday 17 September, 9:00 pm. One week, the same as every module.

## The situation

A folder is gone off a file share and somebody wants a name.

The ticket, the audit export, the asset record and a chat log are in
`course/module_03/M03_evidence/`. Four files, written by four different people for four
different reasons, and no two of them agree about everything.

The ticket asks one question:

> **Who deleted the Q3 folder, and when?**

You are going to find out that one of those two halves is answerable and the other is not, and
the work is being able to say which is which and prove it.

## How this lab works

Five acts. They run in order because each one leaves the next one something to do.

Module 1 asked whether the connection works. Module 2 asked whether the output is true. This
module asks **whether you can design where the platform sits in a piece of work**, which is a
different question and a harder one.

**Twelve checks are marked through the acts, CP1 to CP12.** Each names the thing it looks at.
They exist so that what is being assessed is not a mystery, and so a grader can tell in one
pass. They are not a substitute for reading the acts.

Everything you produce goes in `module_03/` on a branch. Set that up in act 1, not now, and
act 1 will explain why the order matters.

**One thing before you start.** Module 2 had you build the tracking after the work was done,
and said at the time that you would do it the other way round this module and find out why.
This is that.

---

## Act 1: plan it first

Last module you finished the work and then wrote down what you had done. That is a record. It
is not a plan, and the difference shows up the moment something takes longer than you expected,
because a record cannot tell you what you are behind on.

So this time the tracking comes first, before a single file of real work exists.

Through the connector, not by clicking around the GitHub interface:

1. **An issue in GitHub for each act**, five of them. A title, a sentence saying what it
   covers, you as the owner, and a date you actually believe.
2. **Each one attached to `Milestone_01`.**
3. **Each one labelled with the state it is genuinely in**, which right now is all five not
   started.

> **Changed Thursday 18 Sep, 2026.** Two things came out of this step. The project board is
> gone: the connector cannot create one. And "through the connector" no longer applies to the
> milestone, because it cannot create those either, only attach to one that already exists.
> `Milestone_01` is in your repository already and attaching to it is the right move. Create the
> issues through the connector as before. Nobody is marked down for a board or for a milestone
> made by hand, in this module or in module 2.

Then, and only then:

```bash
git switch -c module_03
mkdir -p module_03
```

> **CP1.** Five issues in GitHub exist, each with an owner and a date, **created before the
> first commit of real work.** The commit history is what shows this, so do not backfill it.
>
> **CP2.** All five attached to `Milestone_01`.

### Why the order is the exercise

A plan written first is a claim about the future and it can be wrong, which is what makes it
useful. A plan written last is a description of the past wearing a plan's clothes. It cannot be
wrong, and it cannot tell you anything.

You will also notice that writing the five issues forces you to decide what the five acts
produce before you have done any of them. That is the actual work of planning, and it is
uncomfortable in exactly the way planning is.

**Produces:** five issues in GitHub, each attached to `Milestone_01`, and a branch.

---

## Act 2: the second system

Module 1 connected one system and validated it in both directions. One system is a yes or no
question: the platform can see the thing, or it cannot.

Two systems is a different problem. There is now an order, a direction of travel, and a place
where information leaves one system and arrives in another. That place is the **crossing
point**, and it is where things break, because each system reports its own step succeeding and
nothing reports that the handoff between them did nothing.

### If you already did the connection check

The before-class brief asked you to try this ahead of the session and write
`module_03/connection-check.md`. If that file is in your repository and the connection still
works, CP3 and CP4 are yours. Confirm it still works and go to act 3.

If you did not, or it stopped working, do it now. Nothing is lost either way.

### Connecting it

Your second system is **Google Drive**. You already have institutional Google, it runs in a
browser, and it needs no install and no administrator.

Authorize it the way you authorized version control in module 1. Then validate it the way you
validated that one: **watch information move, in both directions, and be able to describe what
it looked like.** Not a settings screen. A settings screen is a claim a system makes about
itself.

Concretely, and both halves are required:

* Put something in Drive, ask the platform to read it back, and confirm what came back is what
  you put there.
* Have something written into Drive, then open Drive yourself and look at it.

Write both into `module_03/connection-check.md`: what you asked for, what came back, and where
it stopped if it stopped.

> **CP3.** The second system is authorized.
>
> **CP4.** `module_03/connection-check.md` describes a round trip in **both** directions, in
> your own words, naming what you actually saw rather than restating these instructions.

### If Drive will not authorize

It may not. Institutional Google accounts vary and this is the first term this has been tried.

If it refuses, use **GitHub Actions** as your second system instead: a workflow in your own
repository that runs on a trigger and writes a file back. Same crossing point, same round trip,
same two checks. Say in `connection-check.md` which route you took and what the refusal looked
like. Taking the second route costs you nothing.

**Produces:** `module_03/connection-check.md`.

---

## Act 3: the chain

One task, crossing both systems, working end to end. Small is fine. Useful to you is better
than elaborate.

The task itself is yours to choose, and it has to genuinely cross. Reading from one and writing
to the other is a crossing. Reading from both and writing to neither is not.

### Write down where it will break, before it works

In `module_03/prediction.md`, **before you build any of it**:

* Which step you expect to fail.
* Why that step and not another one.

One paragraph. It does not need to be right.

> **CP5.** `prediction.md` exists and its commit predates the working chain. Same rule as act
> 1: the history is the evidence, so do not write it afterwards.

Then build it.

> **CP6.** The chain runs end to end. Something you can look at and immediately tell whether
> it worked.

Then write up what actually happened, in `module_03/chain.md`: what it does, what broke, where,
and how that compares to what you predicted.

> **CP7.** The comparison is there and it is specific. If your prediction was wrong, say why
> you expected differently. A wrong prediction you can explain is worth the same as a right
> one; a working chain with no prediction is worth less than either.

### Why the prediction is the graded part

Every system in your chain reports its own step succeeding. Nothing reports that the handoff
between them did nothing. Knowing in advance where you cannot trust a success message is the
skill, and it is the third time this course has arrived at the same lesson from a different
direction.

**Produces:** `module_03/prediction.md` and `module_03/chain.md`.

---

## Act 4: the investigation

Now the evidence.

Module 2 handed you twenty lines of log and asked whether they supported a conclusion. This is
not that. There are four files, they were written by four different people, and the answer is
not sitting in any one of them.

The platform assists here. It does not answer. You are driving a line of enquiry and using it
for specific questions along the way, which means you have to know what your questions are.

### Start with the question, not the evidence

Before you open a single file, write the question you are answering in one sentence, in
`module_03/investigation.md`.

The ticket asks two things joined by "and". Decide whether that is one question or two, and say
which you are treating it as. That decision shapes everything after it.

> **CP8.** The question is stated in one sentence and its commit predates any analysis file.

### Work the evidence

Read all four files before you ask the platform anything. Then use it: to order events, to
cross-check one artifact against another, to find what you have not thought of. Save the
exchange as `module_03/analysis-session.md`.

Watch for the thing this course keeps warning you about. Something you established early may
quietly stop being honored, and nothing announces it.

> **CP9.** `analysis-session.md` is the actual exchange, prompts included, not a summary of it.

### Take the claims apart

Every distinct factual claim, one per row, in `module_03/critique.md`. **This table format is
defined once, here, and every other file that asks for it points back to this table.**

| Column | What goes in it |
|---|---|
| `id` | `C1`, `C2`, `C3` and so on. You will reference these later, so they have to be stable |
| `claim` | One assertion. One row. No compound sentences |
| `evidence` | **A verbatim quotation from one of the four evidence files**, or the literal `NO EVIDENCE` |
| `type` | Exactly one of `stated`, `inferred`, `unsupported`. No other value |
| `verdict` | Your judgment, and the reason for it |

Two rules on that table, and both are checkable, which is why they are rules and not advice:

* **The quotation has to be findable.** Copy it, do not paraphrase it. A quotation that appears
  in none of the four files fails, and `NO EVIDENCE` belongs only on a row typed `unsupported`.
* **`stated` and `inferred` are different things.** The log says a thing outright, or somebody
  reasoned to it. Output arrives at one confidence level whichever it was. You have to separate
  them.

"I do not know" is a valid verdict and it is the honest one more often than students expect.

> **CP10.** Every row carries an id, a type from the three permitted values, and a quotation
> that can be found in the evidence or a correctly typed `NO EVIDENCE`.

### Four things to speak to either way

There is more in the packet than this. These four you have to address.

1. **The gap.** Something in the packet explains why part of the day has no events. Find it,
   and say what it does to the question.
2. **The deletions that are in the log.** There are some. Are they the ones you were asked
   about? Check the paths and check the access record before you answer.
3. **The chat log against the machine record.** A person says what they did. Does the access
   record agree that they could have?
4. **The person who raised the ticket.** They state when they last saw the folder. Does the
   evidence agree?

### The part that is not determinable

One half of the ticket's question cannot be answered from this evidence. Not "is hard to
answer". Cannot.

Write that as a finding, not as an apology, in a section of `critique.md` headed exactly
`Cannot determine from this evidence`. Say what is missing, and say what would resolve it.
**If you conclude nothing is missing, write the heading and the single word `Nothing`** so that
an absent section and an empty one cannot be confused. That distinction is the entire reason
this heading is mandatory.

**Produces:** `module_03/investigation.md`, `module_03/analysis-session.md`,
`module_03/critique.md`.

---

## Act 5: hand it on

### The finding

`module_03/finding.md`. Half a page, written for Dana Okafor, who raised the ticket, will not
read the audit log, and has a decision to make either way.

Every factual sentence outside the "cannot determine" part carries a **tag** back to the row it
rests on: `[C3]`, or `[C3, C7]` where it rests on more than one. The notation is defined in act
4's table and nothing here changes it.

Three rules, and they are the reason the tags exist:

* An untagged factual sentence is only allowed under the cannot-determine heading.
* **No tag may point at a row you typed `unsupported`.** If a sentence needs one of those, the
  sentence is a claim your own evidence does not carry.
* Keep the tool out of it. Whether the analysis came from a colleague, a vendor or a model does
  not change what the evidence carries, and Dana does not care which.

> **CP11.** `finding.md` is written for a non-specialist, every factual sentence outside the
> cannot-determine part is tagged, every tag resolves to a real row, and no tag points at an
> `unsupported` row.

### The handover

Close your five issues in GitHub **by commit reference**, not by hand. Put `Closes #4` in the
commit message that finishes act 4's work and GitHub does the rest.

This is not tidiness. It ties the record to the work, so the board says what happened rather
than what somebody remembered at the end.

```bash
git add module_03
git commit -m "Module 3: the crossing point. Closes #5"
git push -u origin module_03
```

Open a pull request from `module_03` into your primary branch, **and add your instructor as the
reviewer.** Module 2 you were author and reviewer both, which is not how review works anywhere
else. This time somebody is on the other side of it.

Write the description as a real handover: what is here, what state it is in, what you were
unsure about, and what the reviewer should look at hardest.

> **CP12.** The pull request exists, carries a reviewer, and its description is a genuine
> handover rather than a title. Issues closed by commit reference.

**Produces:** `module_03/finding.md`, a pull request with a reviewer.

---

## What done looks like

On the `module_03` branch, in a pull request with a reviewer on it:

- [ ] five issues in GitHub, created before the work, attached to `Milestone_01`
- [ ] `connection-check.md`, a round trip in both directions, in your own words
- [ ] `prediction.md`, committed before the chain worked
- [ ] `chain.md`, what it does and how it compares to the prediction
- [ ] `investigation.md`, the question in one sentence
- [ ] `analysis-session.md`, the exchange itself
- [ ] `critique.md`, every claim with an id, a type, a findable quotation, and a
      `Cannot determine from this evidence` section
- [ ] `finding.md`, for Dana, every factual sentence tagged
- [ ] a pull request whose description is a real handover

Alongside each of those, the working that produced it. `course/showing-your-work.md` covers
what that means. A correct file with no visible working does not get full credit, and a wrong
file with clear reasoning does not lose it all.

## When it does not work

**Drive will not authorize.** Act 2 covers it. Use GitHub Actions and say what the refusal
looked like. This is a known unknown, not you doing something wrong.

**The platform will not create issues in GitHub.** Reading is one permission and writing is
another. Confirm by asking it to read a file you know exists, then asking it to change
something small. If reading works and writing does not, that is the answer, and it is worth a
line in your journal.

**The platform names a culprit immediately and confidently.** It will. Check the paths and the
access record before you believe it. Confident and wrong is the failure mode this whole course
is built around.

**You cannot tell whether a claim is stated or inferred.** Type it `inferred`, say in the
verdict why you could not tell, and move on. A claim you cannot trace is already a finding.

**You think the answer is "not determinable" for the whole ticket.** Read it again. One half is
answerable and it is worth being precise about which.

**Something else.** Add a `help.me` file to your repository describing where you are stuck, and
push it. A response comes back in the repository, usually within a few hours, and it works even
when nothing else does.
