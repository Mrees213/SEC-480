<h3 align="center">SEC 480: Advanced AI Practicum</h3>

# The handoff

## The situation

Someone left. You have their job.

They left you a note, a ticket, and twenty lines of log, all sitting in `course/module_02/M02_handoff/` in your repository. They did not leave you the part where they explain how they actually did the work,
because that part lived in their head and their head is now on a beach.

Read all three files before you do anything else. `handoff-note.md` first, then `intake.md`,
then `auth.log`.

The ticket asks one question, and somebody needs the answer today:

> **Was the host compromised?**

## How this lab works

Four acts. Each one exists because the one before it left something unfinished, so they run in
order and skipping ahead will not save you time.

Module 1 walked you through the buttons. This does not. You get the situation and the standard
each piece of work has to meet, and the decisions are yours. 

Everything you produce goes in `module_02/` on a branch. Set that up now:

```bash
git switch -c module_02
mkdir -p module_02
```

**One thing to notice before you start.** The note you were left is friendly, confident, and
almost entirely useless. Hold onto how that feels. Act 4 asks you to write one.

---

## Act 1: the process left with the predecessor

Your predecessor says the review is "pretty intuitive once you've done it a few times."

You have done it zero times.

So the first job is not the log. It is writing down the process that should have been in that
note. Not because a lab step says so, but because you cannot do the work without one, and
neither can whoever picks this up after you.

### Do not write it from a blank page

Writing a process from nothing is how you end up with four bullet points and a lie. Instead,
have the platform **interview you**.

Ask it to ask *you* questions about how you would review evidence like this: what you would look
at first, what would make you suspicious, what would make you stop, what you would refuse to
conclude. Answer honestly, including the answers that are "I do not know yet."

Then turn your own answers into the instruction set.

This is worth understanding as a technique, because it comes back all term. You are not
prompting for an answer. You are prompting for the **questions**, and your answers become the
definitions that everything downstream runs on. The questions are the variables.

### You are not starting from nothing

Three instructions are written for you below. Two are missing. Fill those two in from what the
interview surfaced, and change any of the three if your interview told you something different.

```
1. State the question being answered, in one sentence, before reading any log line.
   For: keeps the review scoped to what was asked.

2. Quote the exact log line supporting every claim. Where there is no line, write NO EVIDENCE.
   For: makes an unsupported claim visible instead of letting it blend in with the supported ones.

3. Finish with a section headed "Cannot determine from this evidence", and if it is empty say so.
   For: forces the absence to be a finding rather than a gap the reader has to notice.

4. [yours]
   For:

5. [yours]
   For:
```

Copy that into `module_02/process.md` and work from it.

### The standard it has to meet

Someone else could follow your process, and you could tell from their output whether they had.

That rules out most of what people write first:

| Instruction | Verdict |
|---|---|
| "Be thorough and accurate" | Constrains nothing. No output has ever failed it |
| "Do not make things up" | The same wish, wearing a rule's clothing |
| "Quote the log line supporting every claim, and write NO EVIDENCE where there is none" | Checkable. An output either does this or does not |

**Your two have to pass that test**, and so does anything you change. Under each one, a single
line saying what it is for, because the reasoning is the part that transfers and the rule is the
part that gets misread.

**Produces:** `module_02/process.md`, and the interview session saved beside it.

---


## Act 2: run it on the evidence

Now the log.

Start a fresh conversation, give it the process you just wrote, and run it against `auth.log`
to answer the ticket's question. Save the whole exchange, prompts included.

Do not steer it toward or away from any conclusion. You are not trying to trap anything. You are
finding out what your own process produces when you actually use it.

**Two things will probably happen while you work, and both are content rather than
interruptions.**

Something you established early may quietly stop being honored. Nothing will announce this. If
you notice it, write down where, what you saw, and what you would build into your process so
future-you catches it. If you never notice it, that is also worth knowing about yourself.

You may hit a usage limit. Write down when, and what you were doing. That note is worth marks in
your journal, and working around a rate limit is a skill this course expects you to develop
rather than complain about. Mostly.

**Produces:** `module_02/analysis-session.md`.

**Does not produce:** a verdict. Act 2 ends with you holding an answer you have not checked.
That is deliberate and it is meant to be slightly uncomfortable.

---

## Act 3: your process did not catch it

This is the act everything else was setting up, and it is where most of the marks are.

The analysis you just produced is confident. Confidence is the one thing these systems are never
short of. At least one claim in it is not supported by the twenty lines you were given.

### Take the claims apart

Every distinct factual claim, one per row, in `module_02/critique.md`:

| Column | What goes in it |
|---|---|
| Claim | The assertion, quoted in the platform's own words |
| Type | `stated` if the log says it outright, `inferred` if it was reasoned to, `unsupported` if the log does not carry it |
| Evidence | The line or lines it rests on, quoted, or `none` |
| Verdict | Your judgment, and why |

Splitting `stated` from `inferred` is the whole exercise. The output arrives at one confidence
level throughout, whether a sentence came from the log or from the model's expectation of what a
log like this usually means. Nothing in the writing distinguishes them. You have to.

"I do not know" is a valid verdict and it is the honest one more often than students expect.

### Four things to address specifically

There is more in the log than this. These four are the ones you have to speak to either way.

1. **Order.** Are the entries in the order they appear? Look at the whole timestamp, including
   what is on the end of it, not just the time.
2. **The successful login.** What kind of authentication, which account, from where. Is that the
   same source as the failures?
3. **The accounts being tried.** What does `invalid user` tell you about whether those attempts
   could ever have succeeded?
4. **The end of the file.** What does the last line let you say about what happened next?

Where your analysis got one of these right, quote it and say so. An analysis you can only find
fault with is usually an analysis you have not read properly, and credit where it is due is part
of an honest critique.

### Now the actual point

Go back to `process.md`.

**Your process did not catch what you just caught by hand.** Amend it so it would have. Add the
instruction, and add one line saying what that instruction costs you, because every check you add
is time or tokens you spend on every future review whether it finds anything or not.

Note the change at the bottom of the file: what you added, and what made you add it.

A critique table with a pristine, untouched `process.md` next to it means act 4 did not happen.
It just looks like it did, which is a theme by now.

**Produces:** `module_02/critique.md`, and a revised `module_02/process.md`.

---

## Act 4: hand it on properly

Two deliverables and a handover.

### The finding

`module_02/finding.md`. Half a page, written for Priya, who asked the question, will not read
the log, and needs an answer today.

* What the log actually supports.
* What it does not, including anything your analysis claimed that it should not have.
* What you would need in order to answer the compromise question properly, and why twenty lines
  cannot do it.

Keep the tool out of it. This is your finding. Whether the analysis came from a colleague, a
vendor, or a model does not change what the evidence carries, and Priya does not care which.

### Make the work visible

A handover is not just a document. The next person has to be able to see what state things are
in without reading everything you wrote.

Your repository does not have anywhere for that yet, so build it. You need three things, and you
create all of them **through the connector**, by asking, rather than by clicking around the
GitHub interface:

1. **A milestone named `Milestone 1`.** It covers modules 1 to 3 and closes when Project 1 is
   submitted. Everything you produce this unit attaches to it.
2. **A project board** on your repository.
3. **One issue per act**, four of them, each with a title, a short description of what it
   covered, an owner, which is you, and a date. Attach each one to `Milestone 1` and put it on
   the board in the state it is actually in.

Doing this through the connector rather than by hand is the exercise. It is also the first time
this term you are asking the platform to *change* something rather than read it, which is a
different kind of trust than act 3 asked for.

Yes, you are doing this after finishing the work rather than before. Next module you will do it
first, and you will find out why that is better by having done it the wrong way round once.

### The handover

```bash
git add module_02
git commit -m "Module 2: the handoff"
git push -u origin module_02
```

Open a pull request from `module_02` into your primary branch, and write the description as **the
handoff note you wish you had been given.**

That is the assignment, not a flourish. Go back and reread `handoff-note.md` first. Then write
the one that would have actually helped: what is here, what state it is in, what you were unsure
about, and what the next person should look at hardest.

Then merge it yourself. You are both author and reviewer this module, which is not how review
works anywhere else, and the description is the part that survives that. Module 3 puts somebody
on the other side of it.

---

## What done looks like

On the `module_02` branch, merged into your primary branch through a pull request:

- [ ] `process.md`, with your two instructions filled in, **and the amendment from act 3 with what it cost**
- [ ] the interview session that produced it
- [ ] `analysis-session.md`, the full exchange
- [ ] `critique.md`, every claim typed, evidenced, and judged
- [ ] `finding.md`, written for someone who will not read the log
- [ ] `Milestone 1`, a board, and four issues, one per act, all through the connector
- [ ] a pull request whose description is a real handover

Alongside each of those, the working that produced it. Prompts, what came back, what you changed
and why. `resources/showing-your-work.md` covers what that means. This is graded: a correct file
with no visible working does not get full credit, and a wrong file with clear reasoning does not
lose all of it.

## When it does not work

**The platform cannot see your repository.** The integration has to be authorized and your
repository has to be one it was granted. Renaming a repository can invalidate that. Confirm by
asking for the contents of a file you know exists, not by looking at a settings screen. A green
checkmark is a claim a system makes about itself.

**Your analysis is bland and there is nothing to argue with.** Ask the compromise question
directly. Vague output usually means a vague question, and "analyze this" is about as vague as it
gets.

**You cannot tell whether a claim is inferred or stated.** Good. Log it as `inferred`, say why you
could not tell, and move on. A claim you cannot trace is already a finding.

**Markdown has opinions about your numbered list.** It does. Let it win, the content is what is
being marked.

**Something else.** Add a `help.me` file to your repository describing where you are stuck, and
push it. A response comes back in the repository.
