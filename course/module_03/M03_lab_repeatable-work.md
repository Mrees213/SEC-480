<h3 align="center">SEC 480: Advanced AI Practicum</h3>

# Making work repeatable

**Reference. Keep it. Nothing here is due on its own**, and none of it is part of the module 3
lab. Project 1 requires all three of the things below, so this is where they are explained.

Three techniques, in the order they build on each other:

1. A **Project**, so instructions survive between conversations.
2. An **output contract**, so you state the shape of an answer before you see one.
3. A **Skill**, so a procedure runs on work it has never seen.

Each one is a step further from "I typed a good prompt once" toward "this runs again without
me." That progression is the whole point, and Project 1 is where you are asked to have made it.

---

## 1. A Project: instructions that outlive a conversation

A prompt is a sentence you typed once. An **instruction set** is a policy the platform reads
before every turn and keeps applying. A Project is where that policy lives.

### The thing nobody tells you: check it is actually being applied

A Project can be configured correctly, hold your instructions, show you a green settings
screen, and still not apply all of them. Nothing anywhere says so.

The check takes one prompt. Start a fresh conversation inside the Project, paste nothing, and
ask:

> Repeat my instructions back to me verbatim. Do not summarize them.

Then compare what comes back against what you wrote. Not the gist. Word for word.

### What that check found, the first time it was run here

Five instructions went in. Two came back changed, and both changes removed the part that did
the work.

| Instruction | What was lost |
|---|---|
| "State what the first and last line of the file bound. **Do not describe anything before or after them.**" | The second sentence. The half that constrains anything |
| "Finish with a section headed 'Cannot determine from this evidence', **and if it is empty say so**" | The fallback. Without it, an absent section and an empty section look identical |

The fix was to rewrite both as single sentences with no trailing clause, on the theory that the
trailing clause is what gets dropped. Read back again, both survived.

**The lesson, which is the same one as module 1's:** a settings screen is a claim a system
makes about itself. The read-back is the evidence.

---

## 2. An output contract: state the shape before you see the answer

An output contract is the shape of the answer, written down **before** the answer exists.
Columns, permitted values, required sections, in that order.

You write it first for one reason: once a plausible-looking answer is in front of you, you
grade it against itself. Written down first, you grade it against your own spec.

### A worked contract

| Column | Contents |
|---|---|
| `claim` | One assertion. One row. No compound sentences |
| `evidence` | The quoted line, or the literal string `NO EVIDENCE` |
| `type` | One of `stated`, `inferred`, `unsupported`. No other value |
| `confidence` | `high`, `medium`, `low` |

Followed by a section headed exactly `Cannot determine from this evidence`.

### What came back, and the two failures

The table arrived with four correctly ordered columns. Two things were wrong with it.

**A value not on the list.** One row's `type` read `partially inferred`. The list has three
values and that is not one of them. A person reads straight past it as a nuance. Anything
parsing that column breaks.

**The `Cannot determine` section was missing entirely.** Not empty. Absent. Asking again
produced it.

The second one is the serious one, and it is worth sitting with. An empty section says "nothing
is missing." An absent section says nothing at all, and **it reads as the first.** That is why
the module 3 lab makes you write the word `Nothing` under that heading rather than leaving it
blank.

Neither failure would have been caught without the contract written down first. The table
looked right.

---

## 3. A Skill: a procedure, not a long prompt

A Skill is a named, reusable procedure the platform can pick up and apply. The line between a
Skill and a long prompt is not length.

### The reuse test

**Does it run next module, on different evidence, without editing?**

If the answer is no, it is a long prompt with a filename. Check it by reading your own draft
back looking for anything specific to the work you wrote it for:

| Look for | Should be present? |
|---|---|
| A ticket number | No |
| A filename | No |
| A hostname or an address | No |
| The specific question you were asked | **No. That gets supplied at run time** |
| A date | No |

### The mistake worth borrowing

The first draft of the Skill this section comes from opened with "Determine whether the host was
compromised."

That is one ticket's question, not the Skill's job. Moving the question to something supplied
when the Skill runs is the single change that turned a long prompt into a Skill. Everything else
about it stayed the same.

### The shape of one

A Skill has a name, a one-line description of when to use it, and then the procedure in three
parts: what to establish before starting, how to work, and what to return. The return section is
where your output contract goes.

```
---
name: host-log-review
description: Review a log against a stated question and return a claim table with evidence,
  plus an explicit statement of what cannot be determined. Use for any evidence review where
  somebody has asked a specific question.
---

## Before reading any line

Ask for, or state, the single question this review answers. If it was not supplied, stop and
ask. Do not proceed on an assumed question.

## Reading

1. Normalize every timestamp to a single offset before ordering anything. State the offset.
2. For each event of the kind asked about, record actor, target and source, and state
   explicitly whether each matches the others.
3. Note what the first and last lines bound. Claim nothing outside them.

## Returning

[your output contract goes here]

Then a section headed exactly `Cannot determine from this evidence`, listing what is missing
and what would resolve it. If nothing is missing, write the heading and the single word
`Nothing`. Never omit the section.

## Scope

Report only on what was provided. If asked about a system, timeframe or account not present in
the supplied evidence, say so rather than inferring it.
```

Read that against the reuse test. No ticket, no filename, no hostname, no date, and the question
arrives at run time. That is why it is a Skill.

---

## How the three fit together

| Technique | Answers | Fails silently when |
|---|---|---|
| Project | Do my instructions persist? | They are loaded but not all applied, and nothing says so |
| Output contract | Is the answer the right shape? | A section is absent rather than empty |
| Skill | Does the procedure run on new work? | The old work's specifics are baked in |

All three failure modes have the same shape, and it is the shape this course keeps returning to:
**the system reports success and the thing you wanted did not happen.** A Project with a green
settings screen, a table that looks right, a Skill that only ever ran on the case it was written
for. Each one looks like it worked.

Project 1 asks you to have built all three and to show the checks, not just the artifacts.
