# 03-ideas/

## Purpose

The Idea Bank. Unvalidated sparks, parked concepts, business ideas, content concepts, system improvements, anything the operator might want to come back to but is not committing to today.

The Idea Bank is the place where ideas go to wait without dying. It is not a backlog (a backlog implies eventual execution). It is not a graveyard (a graveyard implies finality). It is a holding pattern with explicit triage on the [weekly rhythm](../../rhythms/weekly.md).

## What goes here

- **Business ideas.** New product directions, service offerings, client-segment ideas. Captured as one-paragraph snapshots, not full briefs.
- **Content concepts.** Topic candidates, hook drafts, format experiments. Most never ship; the ones that do get promoted to `07-content/` as scheduled content.
- **System improvements.** Sparks for changes to the framework itself (a new skill, a different rhythm, a directory restructure). These get evaluated during the [monthly system audit](../../rhythms/monthly.md).
- **Random captures.** Things the operator wants to remember but does not know what to do with yet.

## The graveyard

When an idea is killed during weekly triage, the framework's convention is to *move* it to `03-ideas/graveyard/` rather than delete it. The graveyard preserves the audit trail of "we considered this and rejected it" — useful when the same idea resurfaces six months later and the operator wonders whether they have already made a decision about it.

## The hard cap

The Idea Bank has a hard cap of 15 active items (excluding the graveyard). When the 16th item is captured, the operator triages: promote one to `02-active/` as a sized task, kill several (move to graveyard), or consolidate several into one. The cap is not the point; the *forced triage* is the point. Without the cap, the bank grows linearly until it stops being useful — see [Idea Bank Bloat](../../failure-modes/seven-failure-modes.md#3-idea-bank-bloat).

## Update cadence

Continuously for capture (the operator drops ideas as they appear). Weekly for triage. The bank is allowed to be lossy; what is not allowed is for it to grow indefinitely.

## Permissions

| Actor | Access |
| --- | --- |
| Operator | R/W |
| Local AI agent | Append only |
| Chat AI assistant | Append only |

Both agent classes are append-only because the cost of an agent appending a duplicate or noisy entry is recoverable (the operator triages on the weekly rhythm), but the cost of an agent rewriting a captured idea is loss of the original framing — exactly what the idea layer exists to preserve.
