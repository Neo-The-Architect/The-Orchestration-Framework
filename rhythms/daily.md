# Daily Rhythm

The daily rhythm has three checkpoints: a morning brief that primes the day, continuous capture during the day, and a shutdown reflection that closes the loop. The morning and shutdown checkpoints are short — measured in single-digit minutes — and the capture checkpoint is passive, integrated into the operator's existing workflow rather than added on top.

## Morning Brief — recommended 06:00, agentic

A scheduled job on the [Autonomous Operator](../agentic-stack/03-autonomous-operator.md) composes a brief from the operator's vault state and delivers it through the operator's preferred channel (email, push notification, vault file, or a combination).

The brief draws from:

- **`02-active/` — the current sprint and today's commitments.** What did the operator commit to this week? Which items are due today? Which are blocked?
- **The operator's calendar.** What is scheduled for today? Are there gaps for deep work? Conflicts to flag?
- **A rotating sample of `05-research/` and `09-journal/`.** One or two items the operator wrote or saved recently — the rotating sample surfaces material the operator might otherwise forget they captured.

Output is a short structured document — five to ten short bullets, not a wall of prose. The operator reads it with morning coffee and uses it to decide where attention goes for the day.

## Continuous Capture — throughout the day, agentic

Capture is a passive flow, not a scheduled event. Voice memos, ideas, links, and brain-dump fragments flow into the journal inbox (`09-journal/inbox/`) as they occur. The operator does not stop to decide where each fragment "belongs"; the inbox is the universal capture point.

Two helpers make this work:

- **A brain-dump processor.** A skill or runbook that reads the day's inbox entries and proposes placement: this fragment is an idea (route to `03-ideas/`), this one is a task (route to `02-active/`), this one is just a journal entry (leave in `09-journal/`). Runs on demand, not on a schedule. The operator triggers it when the inbox feels full.
- **A voice-memo transcription pipeline.** The operator records voice memos throughout the day; an inbound automation transcribes them and deposits the transcripts into the journal inbox. The transcription specialist is agnostic to content — it is the brain-dump processor that does the routing.

## Shutdown — recommended 21:00, semi-agentic

A push notification (or equivalent) prompts the operator for a one-line shutdown reflection. The Autonomous Operator appends the response to today's journal file, which is then complete for the day.

The shutdown reflection is deliberately short. The framework is not asking for a journal essay; it is asking for one line that closes the day's loop. Examples:

- *"Shipped the auth refactor. Stuck on the deploy script — pick up tomorrow morning."*
- *"Mostly admin today; tomorrow's first move: draft the proposal for client X."*
- *"Off-day, low energy, did inbox triage and called it. No regrets."*

The cumulative value is in the corpus, not in any single entry. After three months of one-line shutdowns, the operator has a high-fidelity record of what each day actually looked like — searchable, version-controlled, and useful for the weekly and monthly rhythms.

## When the rhythm slips

A missed morning brief is recoverable — read the vault state directly. A missed shutdown is recoverable — append the reflection the next morning, dated correctly. Continuous capture is the one piece that cannot be reconstructed: a fragment lost is a fragment gone. If only one piece of the daily rhythm survives, prioritize the inbox-capture flow.
