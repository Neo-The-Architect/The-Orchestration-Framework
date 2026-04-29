# 3. The Three Layers of State

> Permanent, Active, Idea. Three timescales. Three write protocols. Never mixed.

Human cognition operates on three timescales. Beliefs change rarely. Priorities change weekly. Sparks appear constantly. The Orchestration Framework mirrors this with three architectural layers, each with its own update cadence and write protocol.

- **Permanent layer.** Identity, principles, goals, systems. Updated rarely. Referenced always.
- **Active layer.** This week's focus, current tasks, in-flight projects. Updated daily.
- **Idea layer.** Unvalidated sparks, parked concepts, creative output. Reviewed weekly.

Mixing layers is the most common architectural mistake adopters make. A goal does not belong in the active layer — it is too slow-changing and gets buried under tactical chatter. A task does not belong in the permanent layer — it is too fast-changing and pollutes the constitution. An idea does not belong in either until it has been promoted: an idea entering the active layer without explicit promotion is how the framework starts shipping the wrong things.

The layers also have different write protocols. The permanent layer is operator-only, treated as a constitution: agents may propose changes, but only the operator commits. The active layer is the most agent-permissive: agents read and write freely because the cost of a bad active-layer entry is one day of friction. The idea layer is append-only for agents: capture without curation, with operator-led triage on a weekly rhythm.

## In practice

Suppose the operator drops a thought into the journal: *"I should rewrite the content pillar definitions to emphasize execution over inspiration."* That thought is a spark. It belongs in the idea layer. If it lands directly in the permanent layer (overwriting the existing pillar definitions), the constitution mutates without review. If it lands in the active layer (as a task: *"rewrite content pillars this week"*), the operator commits to specialist work that may not survive contact with the actual content schedule. The correct path: capture in the idea layer, surface at the next weekly review, decide whether to promote to the active layer (as a sized task) or to the permanent layer (as an updated principle), or to drop entirely.

## Related

- [`02-files-over-memory.md`](02-files-over-memory.md) — the layers are file-based, which is what makes them inspectable, versionable, and enforceable. Layers built on AI memory blur into each other within days.
