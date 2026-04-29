# Coordination Pattern

The four roles do not run in parallel as a swarm. They are coordinated, with information flowing in one direction through a sequence of stages, and with the operator inserting decision authority at every stage transition.

## The flow

```
Strategic Counsel  →  vault commit  →  Tactical Builder  →  Specialist Executors  →  vault (as evidence)
       ↑                                                                                    │
       └────────────────── Autonomous Operator (rhythms, captures) ←────────────────────────┘
                                            │
                                            ▼
                                       vault commit
```

Reading the diagram in plain English:

1. The **Strategic Counsel** is where decisions are formed. The operator and the Counsel work through a problem in dialogue. The output is a draft — a decision artifact, a sprint plan, a content brief, a piece of long-form writing.

2. The **operator commits the draft to the vault.** This is the authorization signal. Until the file lands in git, the work is unblessed; once it lands, downstream stages can pick it up.

3. The **Tactical Builder** picks up the committed file and executes against it. It runs commands, builds, tests, ships. Its outputs are code commits, infrastructure changes, and runbook execution logs — also written back to the vault.

4. The **Specialist Executors** are reached by the Tactical Builder (or the Autonomous Operator, or directly by the operator) for deterministic single-purpose work. Their outputs are side effects in external systems plus references written back to the vault as evidence.

5. The **Autonomous Operator** runs in parallel to the human-active flow, on its own schedule, performing rhythms (morning brief, end-of-day capture, periodic indexing). Its writes flow back into the vault, which the Strategic Counsel then picks up on the next interactive session.

## The operator's role

The operator approves the transition between each stage. Specifically:

- **Counsel → vault commit.** The operator decides which drafts get committed and which are rejected or refined.
- **Vault commit → Tactical Builder execution.** The operator hands the work to the Builder and reviews the resulting commits before merge.
- **Tactical Builder → Specialist invocation.** Specialist credentials are scoped narrowly enough that this is usually safe to delegate, but new specialist invocations require operator setup.
- **Autonomous Operator scheduled run → vault changes accepted.** Most rhythms write to append-only or scoped directories where the operator's after-the-fact review is sufficient. Constitutional changes never come from the Autonomous Operator.

This sequence is what keeps the agent stack from becoming a runaway swarm. Every stage is a checkpoint where the operator can intervene, and every stage produces a vault artifact that survives the agents that produced it.

## What goes wrong without this pattern

Adopters who skip the staged flow — who let the Strategic Counsel propose changes that go directly to a Tactical Builder, or let a Tactical Builder hand work to a Specialist without operator review — typically end up with one of two problems:

- **Confidently wrong execution.** Under-specified work flows downstream, the Tactical Builder fills in the gaps with plausible-but-wrong assumptions, and the operator finds out at the end of the chain rather than at the beginning.
- **Audit-trail collapse.** Work happens without ever landing in the vault. Six weeks later, the operator cannot reconstruct what was done or why, and is back to memory-based knowledge — which the framework exists to prevent.

The discipline is to slow down at the boundaries. A vault commit between Counsel and Builder is not bureaucracy; it is the artifact that makes the rest of the framework work.
