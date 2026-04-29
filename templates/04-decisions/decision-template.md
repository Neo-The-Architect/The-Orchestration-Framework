# Decision: {one-line summary}

- **Date:** YYYY-MM-DD
- **Status:** Active
- **Review date:** YYYY-MM-DD (typically 3-6 months out)

## Context

{What prompted this decision? What problem is being solved? What state was the system in just before? Two to four sentences. The reader six months from now should be able to reconstruct what made this decision necessary.}

## Options considered

1. **{Option A}.** {One-paragraph description. What it would look like, what it would require, what its trade-offs are.}
2. **{Option B}.** {Same shape.}
3. **{Option C}.** {Same shape, if applicable. Most decisions have two or three real options; longer lists are usually padding.}

## Decision

{The choice made. One sentence is often enough. If it cannot fit in one sentence, the decision is probably actually two decisions in a trench coat.}

## Reasoning

{Why this option over the others. The reasoning is the part that future-self and agents will read most carefully — this is what lets the next reader know whether the decision should still apply when the context shifts.}

{Three to five sentences. Less is suspicious; more is usually rationalization. If the reasoning runs to many paragraphs, ask whether the underlying decision is well-formed.}

## Consequences

- **Expected positive.** {What this decision unlocks or simplifies.}
- **Expected negative.** {What this decision constrains or makes harder. Be honest. The decision is still defensible if the negatives are real and acknowledged.}
- **Reversibility.** {How hard would it be to reverse this decision? Cheap reversibility makes the decision low-stakes; high reversibility cost makes it high-stakes and the reasoning section should reflect that.}

## Rollback condition

{Under what specific, observable condition would this decision be wrong? Not "if it stops working" — that is too vague. Something like "if the active-sprint sizing exceeds eight items per week for two consecutive weeks" or "if the database write latency p99 exceeds 50ms during normal load." The point is that the operator can detect the rollback condition without re-litigating the original question from scratch.}

## Review notes

(Append below as the decision is reviewed. Each review entry is a short note dated and tagged with the new status. Do not edit prior entries.)

---

<!-- Example future entries:

### YYYY-MM-DD — Reviewed: Active

Still applies. Reasoning unchanged. Next review: YYYY-MM-DD.

### YYYY-MM-DD — Superseded by 2027-01-15-some-other-decision.md

Context shifted: {one-line explanation}. The new decision document captures the current reasoning. This file is preserved for audit but is no longer authoritative.

-->
