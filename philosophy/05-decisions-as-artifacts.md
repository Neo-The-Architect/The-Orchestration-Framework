# 5. Decisions Are First-Class Objects

> Capture reasoning, not just facts. Future-self stops re-litigating solved problems.

Most knowledge systems capture facts but not reasoning. The vault remembers *what* was decided but not *why*, and within months the operator finds themselves making the same decision again — sometimes in the opposite direction — without realizing the question is settled.

The Orchestration Framework treats every non-trivial decision as a discrete artifact with its own file, its own context, its own rollback condition, and its own review date. Decisions live in their own directory, are date-prefixed in ISO format, and are append-only — superseded by new entries, never edited in place. The audit trail is the point: a future reader (operator, agent, prospective collaborator) can reconstruct not just the current state of the system but the reasoning that produced it.

This solves three problems simultaneously. First, future-self never re-litigates solved problems — the decision file is the first place to look before opening the question again. Second, agents reading the vault inherit the operator's reasoning, not just the operator's conclusions; an agent that knows *why* a constraint exists makes better choices when the constraint meets a novel case. Third, drift is detectable — when current behavior contradicts a six-month-old decision, the contradiction surfaces during review. Either the decision is still right (and behavior is wrong), or the decision needs a successor (and the operator can write one with full awareness of what is being overturned).

## In practice

The operator decides early in a project: *use a single shared database with logical separation between services rather than spinning up a database per service*. The decision file captures the reasoning (operational simplicity, single backup pipeline, the team is one person, the per-service cost is not yet justified) and the review date (six months out) and the rollback condition (a second service materially benefits from a different storage engine, or scaling pressure forces the issue).

Three months later, the operator catches themselves about to provision a second database for a new service. The decision file surfaces during the routine pre-action check. The reasoning still applies — the new service's needs fit within the shared database — and the operator avoids re-litigating a question that was already settled with full context. The five minutes spent writing the decision file save an hour of re-deciding.

## Related

- [`02-files-over-memory.md`](02-files-over-memory.md) — decisions captured only in chat are decisions that disappear. The decision-as-artifact pattern is the canonical example of why file-based state is non-negotiable.
