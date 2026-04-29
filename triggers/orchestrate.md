# ORCHESTRATE

> Map the AI tools, agents, and workflows required to execute. Identify which actor performs each step. The operator only appears at decision points.

## What it does

When the operator types `ORCHESTRATE` in a prompt, the AI agent produces an execution plan that names the actor for every step. Steps that an AI agent can do are assigned to the appropriate role from the [agentic stack](../agentic-stack/) (Strategic Counsel, Tactical Builder, Autonomous Operator, or a Specialist Executor). Steps that require a human-in-the-loop decision are explicitly marked as operator steps.

The output is not just a task list. It is an actor-annotated workflow. A well-formed ORCHESTRATE response makes it immediately obvious where the operator's attention is required and where the operator can step away while agents execute.

This is the trigger that operationalizes the [Orchestrator Principle](../philosophy/01-orchestrator-principle.md). Instead of asking "what do I need to do?" — which always lists too many specialist verbs the operator should not be doing — the operator asks "what does the system need to do, and who does each part?"

## When to use

- A multi-step workflow is being planned before execution begins.
- The work spans several agents or tools and the routing is not obvious.
- The operator wants to identify automation opportunities — steps the operator is doing manually today that could route to an agent or a specialist.
- A new project is being scoped and the operator needs to see the actor map before committing to the work.

## When not to use

- A single-step action where there is nothing to orchestrate.
- A decision-formation phase where no plan exists yet to be orchestrated. Use the Strategic Counsel for the decision first; ORCHESTRATE comes after.
- A task that has already been orchestrated. Re-orchestrating without new information is busywork.

## Example prompts

> *ORCHESTRATE: ship a new piece of long-form content next week — research, drafting, editing, publishing, distribution.*

The agent's output, with actor labels:

- **(1)** Research: prior content performance, audience signals, topic adjacency. *Actor: Strategic Counsel.* **Operator step:** review the synthesis, decide topic.
- **(2)** Outline draft. *Actor: Strategic Counsel.* **Operator step:** approve or revise.
- **(3)** First draft from outline. *Actor: Strategic Counsel.* **Operator step:** edit pass.
- **(4)** Format for the publishing platform. *Actor: Tactical Builder if it's a static site, Specialist if it's a CMS connector.*
- **(5)** Publish. *Actor: Specialist (content scheduling platform).* **Operator step:** approve schedule, push.
- **(6)** Distribution: short-form derivatives. *Actor: Strategic Counsel for derivative drafting + Specialist for scheduling.* **Operator step:** approve copy.
- **(7)** Performance pull at end of week. *Actor: Autonomous Operator (existing weekly rhythm).*

The operator now sees that of the seven steps, four require operator attention, and the rest run on rails.

> *ORCHESTRATE: handling inbound press and partnership requests this quarter.*

The agent maps the recurring workflow: inbound channel → triage agent → operator decision on whether to engage → drafting → response. Each step gets an actor. The output reveals which parts could be automated that currently are not.
