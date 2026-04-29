# ITERATE

> Analyze recent data. Identify winners and losers. Cut what is failing. Double down on what is working. Output: a revised plan, not a discussion.

## What it does

When the operator types `ITERATE` in a prompt, the AI agent reads recent data — typically performance logs, sprint outcomes, or experiment results — and produces a *revised plan*. Not a discussion of options, not a balanced analysis of trade-offs. A plan: cut these things, double down on these things, here is the next cycle's commitment.

The trigger forces the agent into convergent mode. Most agentic output is divergent — generate possibilities, weigh trade-offs, leave the operator to choose. ITERATE inverts that: the agent commits to a position based on the data, and the operator either accepts the position, rejects it, or refines it. The mode is decisive on purpose.

## When to use

- A cycle (a sprint, a content week, a campaign, a quarter) has just ended and there is real performance data to read.
- The operator suspects they are spreading effort across too many things and wants the agent to identify the cuts.
- The operator is tempted to "tweak everything a little" and wants forced clarity about what is genuinely working.
- A weekly review (Friday-night content review, Sunday sprint review) where the data is fresh and the next-cycle commitment is being made.

## When not to use

- Early in a project, before there is real data to read. ITERATE without data is opinion masquerading as analysis.
- For decisions that are not really iterative — one-shot decisions where there is no prior cycle to learn from.
- When the operator's energy is low and they are looking for an excuse to cut things they are personally invested in. ITERATE is honest about cuts; if the operator is not ready to accept that honesty, the trigger does more harm than good.

## Example prompts

> *ITERATE: here are the 10 pieces of content I shipped in the last four weeks and the engagement numbers. What's the next month's plan?*

The agent's output: *Top three (X, Y, Z) all share a structural pattern (specific framing, specific hook). Bottom three (A, B, C) share the opposite pattern. Cut the bottom-three pattern. Next month: 6 pieces in the top-three pattern, 2 experiments in directions adjacent to the top-three pattern, 0 pieces in the bottom-three pattern.* Specific, decisive, ready to commit to.

> *ITERATE: I shipped 4 of 8 sprint items last week. What's the next sprint?*

The agent's output: *Half-completion is a sprint-sizing problem, not an execution problem. The 4 unfinished items: 2 were under-specified (recommend kicking back to Strategic Counsel for refinement before re-adding); 2 were genuinely cut by higher-priority work (recommend dropping). Next sprint: 4 items, all from the originally-completed pattern.* The operator can accept or push back, but the agent has done the work of committing to a position.

## What ITERATE will not produce

- *A balanced analysis of all eight items with pros and cons for each.* That is the Strategic Counsel's normal mode. ITERATE skips that mode by design.
- *A discussion of why the data might be misleading.* Methodological caveats are valid, but they belong in a separate prompt. ITERATE assumes the data is what it is and works from there.
- *Permission to keep doing all of it.* If everything is working equally, the data does not actually justify ITERATE — and the agent should say so explicitly rather than fabricating cuts.
