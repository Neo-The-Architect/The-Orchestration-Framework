# The Agentic Stack

The vault is the substrate. The agents are the labor. The Orchestration Framework defines four roles in the stack, each with distinct privileges and responsibilities. Together they form the labor force the operator orchestrates.

The four roles are not specific tools. They are *roles* that any agentic AI tool can fill. Where this section names tools (Claude as a strategic counsel, Claude Code as a tactical builder), those are examples — the framework is deliberately tool-agnostic, and adopters are free to swap in different tools that fit each role's privileges and responsibilities.

| Role | One-line responsibility |
| --- | --- |
| [Strategic Counsel](01-strategic-counsel.md) | Reasoning partner; brainstorming, weekly review, decision discussion, copy drafts |
| [Tactical Builder](02-tactical-builder.md) | Code execution on the operator's machine; builds, refactors, ships |
| [Autonomous Operator](03-autonomous-operator.md) | Scheduled and webhook-triggered work on a server; rhythms, captures, indexing |
| [Specialist Executors](04-specialist-executors.md) | Single-purpose agents and connectors for deterministic specialist tasks |

## How they relate

[`coordination-pattern.md`](coordination-pattern.md) describes the unidirectional information flow between the four roles and where the operator inserts decision authority. Read the four role files first, then the coordination pattern — the pattern only makes sense once you understand what each role is for.

## What this section does not cover

- *How to choose specific tools to fill each role.* Tool selection is left to the adopter. The framework specifies the role and its privileges; the adopter picks the tool whose interface, pricing, and trust model fit their context.
- *How to provision the autonomous-operator host.* That is infrastructure work outside the methodology's scope. The framework assumes the adopter has a hardened VPS or equivalent, accessible from the operator's machine over a secure overlay network.
