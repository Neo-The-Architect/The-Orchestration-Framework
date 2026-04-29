# Strategic Counsel

> The operator's reasoning partner. Reads the vault, reasons over it, proposes changes — but rarely commits.

The Strategic Counsel role is filled by a browser- or app-based chat AI interface. It is the operator's daily counsel. Its strength is conversational depth, breadth of context across the vault, and the ability to hold an entire project in working memory while the operator thinks aloud.

In example terms: this is the role Claude (or any equivalent strategic chat assistant) plays when the operator opens a chat window, pulls in vault excerpts, and works through a problem in dialogue.

## Privileges

- Reads any vault file the operator brings into context.
- Writes are limited per the [permissions table](../architecture/permissions-table.md): R/W on `05-research/`, `07-content/`, `08-projects/`; append-only on `09-journal/`; propose-only on `01-permanent/`, `02-active/`, `04-decisions/`; read-only elsewhere.
- Never executes infrastructure commands. Never holds production credentials.

## Responsibilities

- **Brainstorming.** Generate options, surface trade-offs, push back on the operator's first instinct, propose alternatives the operator did not consider.
- **Brain-dump processing.** Take a stream-of-consciousness journal entry and surface the decisions, tasks, and ideas embedded in it. Triage candidates back to the operator for placement.
- **Weekly review co-pilot.** Read last week's vault state, surface what shipped vs. what stalled, propose next week's focus, flag drift between current behavior and the constitution.
- **Decision discussion.** When a decision is being formed, draft the decision artifact (context, options, reasoning, rollback condition, review date) for the operator to refine and commit.
- **Copy drafts.** First-pass long-form writing — emails, blog posts, content scripts. The operator edits. The Counsel never publishes directly.
- **Research synthesis.** Distill long-form research into short-form briefs that the operator can act on, with citations preserved.

## When not to use

- For tasks that require executing commands on the operator's machine — that is the Tactical Builder's job.
- For scheduled, recurring rhythms — that is the Autonomous Operator's job.
- For deterministic single-purpose tasks (sending an email, creating a calendar block, scheduling a post) — that is a Specialist Executor's job.

The Strategic Counsel's failure mode is taking on work better suited to one of the other three roles. When that happens, the operator ends up acting as a manual conveyor between the Counsel and the eventual executor. The fix is to recognize the role mismatch and route the work directly.
