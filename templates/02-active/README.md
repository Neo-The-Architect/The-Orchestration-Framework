# 02-active/

## Purpose

The active layer. Current sprint, this week's focus, in-flight tasks, the kill list, the not-doing list. Everything the operator is committed to in the present tense.

## What goes here

- **The current sprint.** A small list of items the operator is committed to shipping this week. Two to four items, not ten. The size cap forces honest prioritization; ten-item sprints are wish lists, not commitments.
- **In-flight tasks.** Sub-tasks decomposed from sprint items, partially-complete items, items waiting on a specific blocker.
- **The kill list.** Items that were considered and explicitly rejected — not "maybe later" but "not happening." Recording these prevents the same idea from being re-litigated next week.
- **The not-doing list.** Closely related to the kill list, but for *categories* rather than specific items. *"Not doing video this quarter."* *"Not learning a new framework until the current refactor ships."* Constraints that shape what does and does not enter the sprint.

## What does not go here

- **Goals** (those live in `01-permanent/`; sprint items reference goals but do not redefine them).
- **Unvalidated ideas** (those live in `03-ideas/`; ideas get promoted to the sprint only after the operator commits to working on them).
- **Project-specific working state** (lives inside `08-projects/<project>/`; the sprint references project work but the working files live with the project).

## Update cadence

Daily, in small ways. Weekly, in large ways. The [Sunday review](../../rhythms/weekly.md) sets the sprint; daily activity completes items, marks blockers, and triages additions. The sprint should never be larger at the end of the week than at the start; mid-sprint additions push items off, they do not stack.

## Permissions

| Actor | Access |
| --- | --- |
| Operator | R/W |
| Local AI agent | R/W |
| Chat AI assistant | Propose only |

The local AI agent has full write access because the cost of a bad active-layer entry is one day of friction, recoverable from git. The chat AI assistant proposes (it does not have direct file-write context for the operator's local vault in most setups), and the operator commits.
