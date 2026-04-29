# Tactical Builder

> Runs on the operator's laptop. Full vault read/write. Executes development tasks with git as the safety net.

The Tactical Builder role is filled by a CLI- or IDE-integrated AI agent that can read, write, and execute commands on the operator's local machine. It is the executor of decisions formed in conversation with the Strategic Counsel.

In example terms: this is the role an agentic orchestration tool like Claude Code (or a comparable local-execution AI agent) plays when the operator hands it a typed task and lets it work the local file system, run tests, and produce commits.

## Privileges

- Full read/write on the local vault, subject to [permissions table](../architecture/permissions-table.md) constraints (notably append-only on `04-decisions/` and `09-journal/`).
- Execute shell commands, run builds, run tests, run linters.
- Commit to git, push to feature branches, open pull requests.
- Never merges to `main` without operator authorization (the merge is the operator's decision signal).
- Holds short-lived credentials only — never long-lived production secrets.

## Responsibilities

- **Building features.** Given a typed specification, implement, test, and ship.
- **Refactoring.** Restructure code under git's safety net, with the operator reviewing the diff.
- **Generating boilerplate.** New project scaffolding, config files, repetitive structural code.
- **Executing structured commits.** Follow conventional-commit conventions, write commit messages that describe *why* not just *what*.
- **Running runbooks.** Execute multi-step infrastructure or operational runbooks on the operator's machine, updating `06-infrastructure/` along the way.

## Why local execution matters

Code that runs on the operator's machine is code the operator can inspect, halt, and undo. The Tactical Builder's blast radius is bounded by the operator's local file system and the credentials it has been granted; mistakes are recoverable from git, from filesystem snapshots, or from the operator restarting the agent. Compare this to letting a chat AI propose changes that the operator copy-pastes into a terminal: the chat AI cannot test, cannot iterate, and cannot recover from its own mistakes — the operator becomes the conveyor and the failure-recovery system simultaneously.

## When not to use

- For decisions that have not been made yet — that is the Strategic Counsel's territory. Sending under-specified work to a Tactical Builder produces confidently wrong execution.
- For long-running scheduled work — that is the Autonomous Operator's territory.
- For one-shot specialist actions (send this email, create this calendar block) — those are better routed to a Specialist Executor.

The Tactical Builder's most common failure mode is being handed a task that should have been refined further with the Strategic Counsel first. The fix is to slow down at the boundary: form the decision in chat, write it to a vault file, then hand the file (not just the conclusion) to the Tactical Builder.
