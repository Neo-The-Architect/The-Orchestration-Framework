# Monthly Rhythm

The monthly rhythm has two parts: a system audit and a decision review. The system audit is operator-only — no agents, no chat, no copilot. The decision review is operator-led but reads from agent-prepared material.

The monthly rhythm is the most important rhythm in the framework. It is also the one most likely to be skipped, because its value is invisible until the moment it matters and then catastrophic when it has been skipped for too long.

## System Audit — operator-only, no agents

The system audit is a deliberately low-tech ritual. The operator sits down with the vault, no AI assistant active, and asks four questions:

1. **Does the framework still serve the goals?** Walk the constitution in `01-permanent/`. Is the framework helping the operator get closer to those goals, or has it become its own end? If the operator has spent more time maintaining the framework than shipping work in service of the goals, that is a signal — not an automatic kill, but a signal worth examining.

2. **What is friction?** Where does the operator notice resistance in the daily and weekly rhythms? Friction is data. A morning brief that the operator skips three days in a row is telling the operator something — maybe the brief is wrong for current life, maybe the cadence is wrong, maybe the channel is wrong. Friction surfaces are where the next month's adjustments should aim.

3. **What is over-engineered?** Components that were added "in case" but have not earned their keep. A directory with three files in it after six months. A skill the agent has invoked twice. A trigger word the operator never uses. The framework grows by addition very easily; it shrinks only by deliberate audit.

4. **What should be deleted?** This is the question the audit exists to ask. If nothing is being deleted, the audit is not working. The framework's posture is that components must justify their continued presence; the audit is the moment that justification gets demanded.

The audit produces one output: a short list of changes to make to the framework over the next month. Add a directory, drop a directory, change a rhythm cadence, retire a skill. The operator commits the changes (as a decision artifact, per the [decisions-as-artifacts](../philosophy/05-decisions-as-artifacts.md) principle) and moves on.

## Decision Review — operator-led, agent-supported

The decision log in `04-decisions/` holds every non-trivial decision the operator has made, each with a review date. The monthly decision review walks the entries whose review dates fall in the current month.

For each entry due for review:

- **Active.** The decision still applies; the reasoning still holds. Mark it *Active* and set a new review date if appropriate.
- **Superseded.** Reality has moved past this decision; a successor decision should be written. The original entry is preserved (append-only) and a new decision artifact references it as the supersedence.
- **Reverted.** The decision turned out to be wrong; document what happened, what was learned, and what changes as a result. Like supersession, this preserves the original and adds a successor entry.

The Strategic Counsel can prepare the review by surfacing entries where current behavior contradicts the recorded decision — the drift detection that the decision-as-artifact pattern was designed to enable. The operator decides what to do with each contradiction; the Counsel does not auto-supersede.

## Why monthly and not quarterly

A quarterly cadence would be simpler to maintain but too long to be useful. By the time a quarter has passed, the operator has accumulated three months of unfinished thoughts about the framework and three months of decisions due for review — the rhythm becomes a wall of work, gets dreaded, gets postponed, and eventually gets dropped. Monthly is short enough to fit in a single sitting and long enough that the framework actually changes between audits.

## When the rhythm slips

If the audit has been skipped for two months, schedule it as the first thing to do when picking the rhythm back up — even before resuming weekly reviews. The state of the framework is the substrate everything else runs on; rebuilding daily and weekly rhythms on top of an unaudited substrate is building on a foundation that may already be tilted.
