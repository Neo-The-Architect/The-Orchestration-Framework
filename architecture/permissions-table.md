# Permissions Table

Not every directory is writable by every actor. The framework defines three writers: the operator, the local AI agent (a CLI/code-execution AI running on the operator's machine — for example, an agentic orchestration tool like Claude Code), and the chat AI assistant (a browser- or app-based chat interface — for example, the operator's primary chat AI).

| Directory | Operator | Local AI agent | Chat AI assistant |
| --- | --- | --- | --- |
| `00-meta/` | R/W | R only | R only |
| `01-permanent/` | R/W | R only | Propose only |
| `02-active/` | R/W | R/W | Propose only |
| `03-ideas/` | R/W | Append only | Append only |
| `04-decisions/` | Append only | Append only | Propose only |
| `05-research/` | R/W | R/W | R/W |
| `06-infrastructure/` | R/W | R/W (auto) | R only |
| `07-content/` | R/W | R/W | R/W |
| `08-projects/` | R/W | R/W | R/W |
| `09-journal/` | R/W | R/W | Append only |

## The three constrained protocols

- **R only.** The actor may read but never write. Used where the cost of an erroneous write is catastrophic (`00-meta/` agent configuration, `06-infrastructure/` for the chat AI which lacks the operational context to safely modify infrastructure state).

- **Propose only.** The actor drafts a change and surfaces it for the operator to approve before any write occurs. Used for high-stakes content where agent input is valuable but unilateral writes are not safe — typically the constitution (`01-permanent/`) and the active sprint (`02-active/`) when proposed by the chat AI assistant.

- **Append only.** The actor may add new content but never modify or delete existing content. Used for capture-heavy directories (`03-ideas/`, `09-journal/`) and the decision log (`04-decisions/`, where existing decisions are superseded by new entries rather than edited).

## Why these specific boundaries

The permissions are not arbitrary. They reflect the cost asymmetry of different kinds of damage.

- **Permanent layer is operator-only for write.** The cost of an agent corrupting the constitution is catastrophic — every downstream prompt inherits the corruption, every future agent reads from a poisoned source. Operator-only writes are cheap insurance.

- **Decisions are append-only for everyone, including the operator.** Editing a decision in place erases the audit trail that makes the decision-as-artifact pattern work. The discipline is to write a successor decision that supersedes the prior one, leaving both visible in git history.

- **Ideas and journal are append-only for agents.** The cost of an agent appending a duplicate or noisy entry is recoverable (the operator triages on the weekly rhythm). The cost of an agent rewriting a captured idea is loss of the original framing, which is exactly what the idea layer exists to preserve.

- **The chat AI assistant has narrower writes than the local AI agent.** The chat AI typically lacks the operational context (vault file paths, git state, system commands) to write safely without explicit operator instruction. The local AI agent runs *in* the vault and *in* the operator's environment, so its writes are more easily reversible and more likely to be aligned.

## Auto writes

The "(auto)" annotation on `06-infrastructure/` for the local AI agent means the agent may write autonomously — without per-action operator approval — when executing a runbook that explicitly includes infrastructure-state updates. This is the only directory where agent autonomy is broader than the default. It exists because the alternative (operator approves every infrastructure-state update) creates friction that incentivizes skipping the update entirely, which is worse than the marginal risk of an autonomous write.
