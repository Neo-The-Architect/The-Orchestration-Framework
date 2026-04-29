# 1. The Orchestrator Principle

> The orchestrator controls the tools. The orchestrator does not do the tools' work.

An orchestrator does not write code, design graphics, draft copy, or edit videos. An orchestrator decides, delegates, reviews, and ships. The Orchestration Framework treats this distinction as sacred.

Every task that enters the system is filtered through the verb test. If a task begins with *write*, *code*, *design*, *record*, or *edit*, it is specialist work and must either be (a) decomposed into orchestration verbs, or (b) delegated to an agent. Specialist verbs in the operator's queue are an architectural failure, not a workload problem.

This is the principle that the rest of the framework defends. The vault structure separates orchestration state from specialist output. The agent stack matches each specialist verb to an executor. The rhythms surface specialist creep before it ossifies. None of those mechanisms work if the operator is willing to retake specialist work whenever the queue is short or the agent is slow.

## In practice

Suppose the work is *ship a landing page for a new product*. The orchestrator's tasks are: decide the hero direction, approve the visual style, review the copy, merge the PR, push to production. The specialist tasks — *write the hero copy*, *design the hero illustration*, *code the responsive grid*, *edit the explainer video* — belong to agents and tools. If the orchestrator's todo list contains "write hero copy," the system has failed before the work began. Either the operator restates the task as "approve hero copy direction (three options drafted by the agent)" or the agent has not been given enough context to draft on its own — and the fix is to give it that context, not to reach for the keyboard.

## Related

- [`02-files-over-memory.md`](02-files-over-memory.md) — orchestration is mediated through files; specialist output lands in files; the operator reviews files. The two principles compose: orchestration without file-based state collapses into chat, where decisions evaporate the moment the window closes.
