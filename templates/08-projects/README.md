# 08-projects/

## Purpose

Per-project working directories. One subfolder per active project. Project-internal organization is at the operator's discretion — the framework specifies that each project gets its own directory and that work is bounded by that directory, not what the inside of each project looks like.

## What goes here

- **One subfolder per active project.** Each subfolder is named with the project's working name (per the [naming-paralysis countermeasure](../../failure-modes/seven-failure-modes.md#4-naming-paralysis): a working name is mandatory at project creation and revisable later).
- **Inside each project subfolder:** whatever the project needs. Project-specific notes, project-specific decisions (as a project-scoped successor to or supplement to `04-decisions/`), project-specific infrastructure references, project-specific content drafts, sub-project tasks. The framework does not prescribe internal structure.

## What does not go here

- **Cross-project principles** (those live in `01-permanent/` and are read-only to projects).
- **Universal infrastructure** (lives in `06-infrastructure/`; project-specific infrastructure goes inside the project subfolder).
- **The active sprint** (lives in `02-active/`; the sprint references project work, but the project files live with the project).
- **Personal journal entries** (live in `09-journal/`, even when they are about project work).

## Project lifecycle

A project enters `08-projects/` when the operator commits to it. The commitment moment is also when a working name is assigned. Projects exit the directory when they ship (move to a `08-projects/_archive/` or equivalent) or when they are killed (move to a graveyard or deleted, depending on how recoverable the operator wants the work to be).

The framework does not enforce project boundaries beyond the directory boundary. If the operator works on three projects in parallel, three subfolders exist; if work bleeds across projects (see [Cross-Project Bleed](../../failure-modes/seven-failure-modes.md#7-cross-project-bleed)), the directory boundary is the discipline, and the operator's job is to resist the temptation to "hoist" project-specific content into the permanent layer prematurely.

## Update cadence

Continuously per active project. Each project's update cadence depends on what the project is. Some projects move daily; some move weekly; some sit dormant and reactivate when the operator returns to them.

## Permissions

| Actor | Access |
| --- | --- |
| Operator | R/W |
| Local AI agent | R/W |
| Chat AI assistant | R/W |

All actors have full access within `08-projects/`. The agent stack collaborates heavily on project work — drafting, building, reviewing, shipping. The audit-trail concerns that govern other directories (decisions, journal) apply only weakly here; for important project decisions, the operator promotes the artifact to `04-decisions/` rather than relying on the project subfolder for the audit trail.
