# 00-meta/

## Purpose

System files for the agent stack. This directory holds the configuration, skill definitions, templates, and the killswitch file that every agent in the stack reads before acting.

## What goes here

- **Agent configuration files.** A `CLAUDE.md` (or whatever the equivalent is for the AI agent the operator uses) that gives the agent context about the vault, the operator, and the conventions to follow.
- **Skill definitions.** Reusable prompt patterns or workflows the agent can be invoked with — for example, the brain-dump processor, the orchestrator-guard verb-checker, the weekly-review co-pilot.
- **Templates.** The canonical `.template` files that get copied into other directories when instantiating a new file (a new decision, a new daily journal entry, a new project).
- **The killswitch file.** A single file that every agent reads at the start of every non-trivial action; if it contains a HALT directive, the agent stops.

## Update cadence

Rarely, deliberately. `00-meta/` is the foundation; changes ripple through the entire agent stack. The operator updates this directory in conscious sessions — typically as part of the [monthly system audit](../../rhythms/monthly.md) — not in the flow of daily work.

## Permissions

| Actor | Access |
| --- | --- |
| Operator | R/W |
| Local AI agent | R only |
| Chat AI assistant | R only |

`00-meta/` is operator-only for write because the cost of an agent corrupting its own configuration is a recursively unrecoverable failure: a misconfigured agent might propose a "fix" that makes its configuration even more wrong, and the operator's audit becomes the only correction path. Operator-only writes are cheap insurance.

## Files in this template

- [`killswitch.md.template`](killswitch.md.template) — the killswitch skeleton; copy to `00-meta/killswitch.md` in your vault and never delete it.
