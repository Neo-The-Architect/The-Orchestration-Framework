# Autonomous Operator

> Runs on a hardened VPS as a scheduled or webhook-triggered agent. Narrow, scoped permissions. Source-of-truth flows from the operator's machine, not from the VPS.

The Autonomous Operator role is filled by a CLI-based AI agent running unattended on a server. It handles work that needs to happen without the operator present: morning briefs, end-of-day captures, research indexing, scheduled content pulls, periodic infrastructure-state updates.

In example terms: this is the same agentic orchestration tool that fills the Tactical Builder role, but running on a VPS rather than the operator's laptop, triggered by cron or webhook rather than by the operator typing.

## Privileges

- Reads from a vault copy that syncs from the operator's primary device. The laptop is the source of truth; the VPS is a working copy.
- Writes are scoped narrowly per the runbook the agent is executing. A morning-brief agent writes only to `07-content/` or `09-journal/`; an infrastructure-state-updater writes only to `06-infrastructure/`.
- Holds long-lived credentials only as required for the specific task and only at the minimum scope.
- Never holds the operator's primary identity — operates as a separate, narrow service identity with its own access controls.

## Responsibilities

- **Morning brief composition.** Compose a daily brief from active sprint, calendar, and a rotating sample of recent research and journal entries. Deliver via the operator's preferred channel (email, push notification, vault file).
- **End-of-day journal capture.** Prompt the operator for a one-line shutdown reflection (push notification or equivalent). Append the response to today's journal file.
- **Research indexing.** Process newly-added research artifacts in `05-research/`, generate summaries, build cross-link suggestions for the operator to review.
- **Infrastructure-state updates.** Periodically check the live state of services and update `06-infrastructure/service-inventory.md` (or equivalent) so the vault's view of infrastructure does not drift from reality.
- **Content performance pulls.** Pull metrics from connected content platforms on a schedule, write the data to `07-content/performance-log.md`, flag outliers.
- **Voice-memo transcription.** Watch a designated inbox for voice-memo uploads, transcribe, deposit into `09-journal/inbox/` for the operator's review.

## The synchronization rule

The vault on the laptop is canonical. The vault on the VPS is a working copy. When they disagree, the laptop wins.

This rule exists because the laptop is the operator's primary thinking surface — every decision starts there, every constitutional change starts there. The VPS is a labor server, not a knowledge server. If the operator's laptop is offline for a week and the VPS keeps writing to its own copy, the merge back is straightforward (VPS writes are append-only or scoped to specific directories) and the laptop's version always trumps in conflict resolution.

## When not to use

- For decisions or constitutional changes — those flow through the Strategic Counsel and land via operator commits on the laptop.
- For tasks where the operator's interactive judgment is needed mid-flight — those belong to the Tactical Builder.
- For one-shot specialist tasks — those route to Specialist Executors.

The Autonomous Operator's failure mode is mission creep: a single-purpose runbook gradually accumulates side concerns ("while we're in there, also update this other file") until the agent's writes can no longer be audited as a single coherent action. The fix is one runbook = one purpose, with separate runbooks (and separate scheduled invocations) for separate purposes.
