# Output Contract

This contract defines the required structure of the evidence analysis before the analysis is generated.

The response must contain a table with the following columns in exactly this order:

`id | claim | evidence | type | verdict`

## Requirements

Each row must contain one factual claim.

The `evidence` field must contain either:

- a verbatim quotation from the supplied evidence, or
- the literal string `NO EVIDENCE`.

The `type` field must contain exactly one of:

- `stated`
- `inferred`
- `unsupported`

No other value is permitted.

The `verdict` field must explain whether the evidence supports the claim and why.

The response must finish with a section headed exactly:

`Cannot determine from this evidence`

If nothing belongs in that section, it must contain the single word:

`Nothing`

The analysis must not make claims about systems, accounts, actions, times, or events that are not supported by the supplied evidence.
