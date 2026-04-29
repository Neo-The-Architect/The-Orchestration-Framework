# 06-infrastructure/

## Purpose

The vault's view of the operator's infrastructure. VPS state, service inventory, runbooks, secrets index (names only, never values), network topology, deployment notes.

This directory is the source of truth for "what infrastructure does the operator currently run, where does each piece live, and how is it operated?" It is read by the [Autonomous Operator](../../agentic-stack/03-autonomous-operator.md) when executing infrastructure-state updates and by the operator (and the Strategic Counsel during planning sessions) when scoping new work.

## What goes here

- **Service inventory.** A table or list of every service the operator runs, where it runs, what it depends on, what state it persists, who can reach it. Updated whenever the inventory changes.
- **Runbooks.** Step-by-step procedures for repeatable operations: install a new service, rotate a credential, deploy a new version, recover from a specific failure mode. Each runbook is self-contained and references the service inventory by name.
- **Architecture decisions specific to infrastructure.** Cross-link to `04-decisions/` rather than duplicating; this directory references the decision files but does not redefine them.
- **Secrets index.** A list of which secrets exist (Postgres password for service A, API key for service B, etc.) and where the actual values live (a password manager, a secrets vault, an environment file outside the vault). The values themselves never live here. The index just lets the operator answer "what credentials does this system depend on?" without grepping for secret material.
- **Network and access topology.** Which services are reachable from where, what auth gates them, what the overlay-network or VPN posture is.

## What does not go here

- **Cleartext secret values.** The vault is read by every agent in the stack and committed to git. Cleartext secrets in this directory are a recurring source of breach incidents.
- **Per-project infrastructure files** (those live inside `08-projects/<project>/infra/` or equivalent).
- **Application code or configuration that lives in a separate project repo.** The vault references the project repo by URL or path; the actual files live with the project.

## Update cadence

Continuously when infrastructure changes. Periodically (monthly or as part of the system audit) to verify the vault's view of infrastructure has not drifted from the actual state. The Autonomous Operator may run scheduled drift-checks that compare live state to the inventory and flag mismatches.

## Permissions

| Actor | Access |
| --- | --- |
| Operator | R/W |
| Local AI agent | R/W (auto) |
| Chat AI assistant | R only |

The local AI agent's `R/W (auto)` annotation means the agent may write autonomously *when executing a runbook that explicitly includes infrastructure-state updates*. This is the only directory where agent autonomy is broader than the default. The chat AI assistant is read-only because it lacks the operational context (live system state, current credentials, current deploy state) to write safely.
