# 4. Token Efficiency Is Discipline

> Lean output is an engineering constraint, not a stylistic preference.

Every word in the vault is read by both humans and agents. Fluff costs context window space. Repetition costs review time. Restating in long form what could be said in short form costs everything downstream.

This principle is what separates a vault that serves the operator from a vault that performs the operator. Performative writing — explanatory preambles, hedged conclusions, throat-clearing transitions — is the default register of someone trying to impress a reader. Functional writing is the register of someone trying to be understood by a reader who has work to do. The vault should be the second.

The cost is real and compounding. A 200-word file that conveys what a 40-word file would conveys it five times more expensively. The agent reading it spends five times the tokens; the operator reviewing it spends five times the time; downstream agents inherit the bloat in every retrieval, every summary, every prompt-window inclusion. At small scale this is invisible. At hundreds of files, it is the difference between a vault that answers questions in seconds and one that answers them in minutes.

## In practice

A decision file drafted in a long, narrative voice runs 600 words: *"After much deliberation, considering several alternatives, weighing the trade-offs between X and Y, and consulting on the implications for our broader architecture, we have arrived at the conclusion that..."* The same decision in functional voice runs 80 words: *"Decision: X. Reasoning: Y is incompatible with our authentication boundary. Alternatives considered: Z (rejected, locks us into vendor A). Review: 6 months. Rollback: revert PR #42."* Both files capture the same information. The functional one is faster to review, cheaper to retrieve, and easier for an agent to summarize. There is no upside to the long version except prose that reads as more authoritative — which is exactly the cost.

## Related

- [`02-files-over-memory.md`](02-files-over-memory.md) — files are the input every agent reads. Token efficiency is the discipline that keeps the files-over-memory architecture from becoming files-over-everything-the-agent-can-still-fit.
