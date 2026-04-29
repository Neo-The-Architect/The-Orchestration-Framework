# Weekly Rhythm

The weekly rhythm has two parts: a Sunday review (or whatever day the operator chooses as their week-boundary) and a content performance pull on Friday. The Sunday review is operator-led, agent-supported. The performance pull is agent-led, operator-reviewed.

## Sunday Review — operator-led, agent-supported

The Sunday review is the highest-leverage rhythm in the framework. Sixty minutes per week, executed honestly, prevents most of the failure modes the framework anticipates.

The review covers five things:

1. **Archive what shipped.** Move completed items out of the active sprint into wherever they are kept (per-project archives, a "shipped" log, or just deleted if no archive is needed). The active sprint should not accumulate completed work.

2. **Kill what stalled.** Items that have been in the active sprint for two weeks without movement are candidates for the kill list. Either the operator commits to shipping them this week or they get archived as deliberately-killed. The middle option — leaving stalled items on the sprint — is what produces sprint bloat and learned helplessness toward the sprint as a planning instrument.

3. **Triage the idea bank.** Walk `03-ideas/`. Promote the ideas worth working on (move to `02-active/` as sized tasks). Drop the ideas that are no longer compelling (move to a graveyard subdirectory or delete). The idea bank is allowed to be lossy; what is not allowed is for it to grow indefinitely.

4. **Set next week's focus.** Decide what the operator is committed to shipping in the coming week. Two to four items, not ten. The active sprint is a commitment, not a wish list — the size cap forces the operator to prioritize honestly.

5. **Goal pulse.** A one-line check on each of the operator's goals (whatever the operator's goal-list looks like in `01-permanent/`). *Am I closer to this goal than I was last week, or further away, or unchanged?* The pulse is qualitative; the value is in noticing the trend, not in measuring it.

## How the Strategic Counsel supports

The [Strategic Counsel](../agentic-stack/01-strategic-counsel.md) reads last week's vault state and proposes: which items are stalled, which ideas are worth surfacing, which goals show drift. The operator decides what to act on. The Counsel never commits the next sprint directly — proposing the sprint is the Counsel's job; deciding the sprint is the operator's job.

A useful pattern: the operator opens a chat with the Counsel, pastes in or refers the Counsel to the relevant vault sections, and works through the five steps in dialogue. The output is a draft sprint plan, a proposed kill list, and a triaged idea bank — all of which the operator commits to the vault as the closing act of the review.

## Content Performance Pull — Friday, agentic

The [Autonomous Operator](../agentic-stack/03-autonomous-operator.md) pulls metrics from the operator's connected content platforms on Friday and writes them to `07-content/performance-log.md`. The agent does three things:

1. Records the raw metrics for each piece of content published that week.
2. Flags the top three and bottom three performers — the outliers.
3. Surfaces patterns *only when they are obvious from the data alone*. The Counsel and the operator do the deeper pattern analysis during the Sunday review.

The Friday pull is deliberately separated from the Sunday review by a buffer day. This lets the metrics settle (most platforms continue to attribute engagement for several hours after publication) and gives the operator a chance to look at the raw data on Friday or Saturday before the review forces a synthesis on Sunday.

## When to skip and when not to

A skipped weekly review will not destroy the framework. A pattern of skipped weekly reviews will. After two consecutive misses, the operator should treat the next review as a recovery review — slightly longer, with explicit attention to *what slipped while the rhythm was off* — rather than just resuming as if nothing happened.
