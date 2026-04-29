# 09-journal/

## Purpose

Daily notes, raw brain dumps, voice transcription inbox, end-of-day shutdown reflections. The unprocessed feed of the operator's day-to-day reality.

The journal is the universal capture point. It is where things land before the operator (or a brain-dump processor) decides where they really belong. A thought that might be an idea, a task, a decision-in-formation, or just a passing reflection — it goes in the journal first and gets routed during processing.

## What goes here

- **Daily entries.** One file per day, date-prefixed: `2026-04-29-journal.md`. The day's running notes, the end-of-day shutdown reflection, anything the operator wants attached to a specific date.
- **The capture inbox** (typically `09-journal/inbox/`). Short fragments — voice memos transcribed, web links saved, sparks captured — that have not yet been processed into placement decisions.
- **Voice-memo transcripts.** As the [daily rhythm](../../rhythms/daily.md) describes, an inbound automation deposits transcripts here. The brain-dump processor (or the operator) routes them downstream.

## What does not go here

- **Already-processed ideas** (those move to `03-ideas/` after triage).
- **Decisions** (move to `04-decisions/` once they are formed enough to warrant a decision artifact).
- **Project notes that are clearly project-scoped** (move to `08-projects/<project>/`).

The journal is fast capture. Routing happens *after* capture, not during. Don't slow down the capture flow by deciding placement upfront — that is what the brain-dump processor is for.

## Update cadence

Continuously throughout each day for capture. Daily for shutdown reflections. Weekly during the Sunday review for any unprocessed inbox entries that the brain-dump processor did not route automatically.

## Permissions

| Actor | Access |
| --- | --- |
| Operator | R/W |
| Local AI agent | R/W |
| Chat AI assistant | Append only |

The chat AI assistant is append-only because journal entries are dated artifacts — modifying yesterday's journal entry retroactively damages the audit trail of what the operator was actually thinking on that day. Append-only preserves the time-truth of the journal even when an agent has new information to contribute.

## Files in this template

- [`daily-journal-template.md`](daily-journal-template.md) — daily entry skeleton; copy as `YYYY-MM-DD-journal.md` for each new day.
