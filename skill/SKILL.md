# Evidence Review Skill

## Purpose

Review a supplied artifact against a user-provided analysis question using only the evidence contained in that artifact.

## Inputs

The user must provide:

1. An artifact to analyze.
2. A specific analysis question.

Do not assume facts that are not present in the supplied artifact.

## Procedure

1. Read the complete supplied artifact.
2. Identify the important factual claims needed to answer the analysis question.
3. Separate each claim into exactly one of these types:
   - stated
   - inferred
   - unsupported
4. For every stated or inferred claim, quote the exact evidence from the supplied artifact.
5. If a claim has no supporting evidence, write:

   `NO EVIDENCE`

6. Do not rely on outside knowledge unless the user explicitly asks for it.
7. Do not make claims about systems, users, dates, files, execution results, or behavior that are not supported by the supplied artifact.
8. Keep the answer focused only on the stated analysis question.

## Output Format

Use this table:

| id | claim | evidence | type | verdict |
|---|---|---|---|---|

Use sequential claim IDs:

`C1`, `C2`, `C3`, etc.

The `type` field must contain exactly one of:

- stated
- inferred
- unsupported

For unsupported claims, evidence must be:

`NO EVIDENCE`

After the table, include a section headed exactly:

## Cannot determine from this evidence

List anything relevant to the analysis question that the supplied artifact cannot establish.

If nothing belongs in that section, write:

Nothing
