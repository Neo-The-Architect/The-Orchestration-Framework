# Trigger Words

Triggers are single keywords the operator types to invoke a specific operational mode in any AI agent in the stack. They are the operator's API for steering behavior without re-explaining context every time.

The framework defines three triggers, deliberately. More triggers would dilute the contract; fewer would leave common needs unaddressed. Each one corresponds to a specific cognitive mode that the operator routinely needs from the agent.

| Trigger | Mode | When to use |
| --- | --- | --- |
| [`GAMIFY`](gamify.md) | Decompose into small, momentum-driven tasks | When the work is large, daunting, or the operator's energy is low |
| [`ORCHESTRATE`](orchestrate.md) | Map the agents, tools, and steps required to execute | When planning a multi-step workflow before execution begins |
| [`ITERATE`](iterate.md) | Analyze recent data, cut what fails, double down on what works | When making the next-cycle plan informed by the last cycle's results |

## How they work

The triggers are a convention, not a feature of any specific tool. Any AI agent the operator interacts with — Strategic Counsel, Tactical Builder, Autonomous Operator — recognizes the trigger word in a prompt and shifts its output accordingly. The convention is shared across the stack, so the operator does not have to remember which mode each tool natively supports; the trigger is the universal API.

For the convention to work, the agent needs to know what each trigger means. In practice this is set up by including a brief summary of the triggers in the agent's system prompt, configuration file, or skill definition. The summary can point at this directory for the full description.

## When not to use

- *When the prompt is already clear without the trigger.* Triggers are for invoking a mode, not for decoration. A well-specified prompt often does not need one.
- *When the operator does not yet know what mode they want.* Reaching for a trigger as a way to avoid forming the question is how the operator ends up with confidently-wrong output. Form the question first; choose the trigger when the mode is genuinely needed.
- *When the work is too small to benefit.* A two-line task does not need GAMIFY. A single-step action does not need ORCHESTRATE. Triggers earn their keep on work that has enough structure for the mode to operate over.
