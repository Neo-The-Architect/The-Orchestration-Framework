# 01-permanent/

## Purpose

The slow-changing constitution. Identity, principles, the operator's goals, personal systems, key facts. This is the layer the rest of the framework reads from when an agent needs to know "who is this operator and what do they care about?"

## What goes here

- **Identity statements.** Who the operator is, what they do, what their public-facing positioning is.
- **Principles.** The rules the operator commits to operating under. Distinct from the Orchestration Framework's six [philosophical principles](../../philosophy/) — those are framework-level. The operator's personal principles are the next layer down.
- **Goals.** Whatever goal-list structure the operator works with. The framework does not prescribe a specific goal architecture; it requires that goals exist in this directory and are referenced (not redefined) elsewhere.
- **Personal systems.** Recurring routines, habits, structures that hold across projects (morning routine, exercise cadence, sleep schedule, learning loop).
- **Key facts.** Stable reference data that agents need to know but does not change often (the operator's primary timezone, default working hours, important relationships, fixed commitments).

## What does not go here

- **This week's tasks** (those are `02-active/`).
- **Unvalidated ideas** (those are `03-ideas/`).
- **Project-specific principles** (those live inside `08-projects/<project>/`).
- **Decisions that have specific review dates** (those are `04-decisions/`).

The most common adoption mistake is putting too much in `01-permanent/`. When in doubt, the content is probably project-scoped or time-anchored and belongs elsewhere.

## Update cadence

Slow. Days, weeks, months between meaningful updates. If `01-permanent/` is changing every week, the operator is probably mistaking active sprint content for constitutional content.

## Permissions

| Actor | Access |
| --- | --- |
| Operator | R/W |
| Local AI agent | R only |
| Chat AI assistant | Propose only |

The chat AI assistant may propose changes (drafts a successor file, surfaces it for the operator to commit) but never writes to this directory directly. The cost of an agent corrupting the constitution is catastrophic — every downstream prompt inherits the corruption. Operator-only writes (with agent proposals as input) is the only safe protocol here.
