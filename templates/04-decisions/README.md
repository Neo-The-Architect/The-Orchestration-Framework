# 04-decisions/

## Purpose

The decision log. One file per non-trivial decision, date-prefixed in ISO format, append-only. The canonical record of *what* the operator decided and — more importantly — *why*.

This directory operationalizes the [decisions-as-artifacts](../../philosophy/05-decisions-as-artifacts.md) principle. Every entry captures not just the conclusion but the reasoning, the alternatives considered, the rollback condition, and the review date. Future-self stops re-litigating solved problems; agents inherit the reasoning, not just the conclusion; drift between current behavior and prior decisions becomes detectable during the [monthly decision review](../../rhythms/monthly.md).

## What goes here

- **Architectural decisions.** Choices that shape the system the operator builds — frameworks, services, database choices, deployment strategies.
- **Operational decisions.** Choices that shape how the operator works — tools adopted, tools dropped, rhythms changed, skills added.
- **Strategic decisions.** Choices about direction — what to focus on, what to defer, what to kill.
- **Personal decisions** *that have lasting impact.* Not every personal choice belongs here; the threshold is whether the operator might reasonably revisit the question in the future.

## What does not go here

- **Trivial choices.** "Used Postgres for this small project" does not need a decision artifact unless the choice was non-obvious or the operator might reverse it.
- **Implementation details.** "Used a hash map instead of a list for this lookup" is a code comment, not a decision artifact.
- **Predictions.** Decisions are commitments; predictions are guesses. "I think X will happen" goes in the journal, not the decision log.

## File naming

Files are date-prefixed in ISO format and given a slug:

- `2026-04-29-postgres-single-instance-shared-process.md`
- `2026-04-29-tailscale-ssh-as-primary-access-path.md`
- `2026-04-29-rename-product-line-from-X-to-Y.md`

Date sorting is automatic; slug retrieval works with any grep-like tool. When a decision is superseded, the new decision references the old by filename.

## Update cadence

Whenever a non-trivial decision is made. The decision artifact is written *as part of* making the decision, not after. Drafting the file is part of the decision-formation process; if the operator cannot articulate the reasoning well enough to write the file, the decision is not yet ready to commit.

Existing files are append-only — *never edited in place*. When a decision is superseded or reverted, a *new* file is written with the new decision, referencing the prior one. Both files remain in the directory; the original captures what was true at the time, and the successor captures what changed.

## Permissions

| Actor | Access |
| --- | --- |
| Operator | Append only |
| Local AI agent | Append only |
| Chat AI assistant | Propose only |

The operator's permission is `Append only` (not R/W) deliberately — even the operator does not edit decisions in place. This preserves the audit trail and prevents the operator from rewriting history when the original decision turns out to be wrong.

## Files in this template

- [`decision-template.md`](decision-template.md) — the decision-artifact skeleton; copy and fill in for each new decision.
