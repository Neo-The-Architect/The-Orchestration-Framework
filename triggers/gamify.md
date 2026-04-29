# GAMIFY

> Decompose the work into small, dopamine-driven tasks. Maximum 30-minute units. Sequenced for momentum, not optimization.

## What it does

When the operator types `GAMIFY` in a prompt, the AI agent breaks the work into the smallest unit that produces a visible win. Each unit must be completable in 30 minutes or less. The sequence prioritizes momentum — early wins, fast feedback, satisfying-to-finish tasks first — over the theoretically-optimal order.

This is deliberately *not* what most planners do. Most planners optimize for dependency order or critical path. GAMIFY optimizes for the operator's energy economy. The premise is that getting started and staying in motion is the rate-limiting constraint on most work, not raw efficiency.

## When to use

- The work is large and the operator is staring at it without starting.
- The operator's energy is low and a 30-minute win is more achievable than a four-hour deep-work block.
- The work has a natural sequence of small completable steps that build on each other (drafting a long document, refactoring a codebase, processing a backlog).
- The operator wants to ship something today rather than plan optimally for tomorrow.

## When not to use

- The work has hard dependencies that force a specific order. GAMIFY's "sequence for momentum" is wrong if step 3 cannot start until step 1 and step 2 complete; in that case, the dependency order is the only valid order.
- The work is small enough that decomposition adds more overhead than it removes.
- The operator is already in deep work flow. Don't interrupt momentum to formalize it.

## Example prompts

> *GAMIFY: I need to migrate fifty user accounts from the old auth system to the new one.*

The agent's output: a sequence of 30-minute or smaller chunks — *(1) export current users to CSV, verify count; (2) write the mapping script for the first 5 users; (3) run on those 5, verify output; (4) run on next 10; (5) run on next 15; (6) run on the final 20; (7) decommission the old system; (8) write the migration-complete entry in the decision log.* Each step is small enough to complete in a sitting and produces visible progress.

> *GAMIFY: I have a 4,000-word draft of the proposal that needs to ship by Friday.*

The agent's output: not "edit the proposal" (too large, no momentum) but a sequence — *(1) read once, mark sections; (2) revise the introduction; (3) revise section one; (4) revise section two…* and so on, with each section a self-contained 20-30 minute unit.
