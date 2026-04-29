# 6. The Killswitch Is Sacred

> The orchestrator must always be able to stop the orchestra.

A fully agentic system must always be stoppable. The operator must, at all times, be able to halt every agent in the stack with a single action. This is not a feature — it is a precondition for granting agents write access to anything.

The killswitch lives as a designated file in the vault's meta directory. Every agent, before performing any non-trivial action, reads the killswitch file. If the file contains a HALT directive, the agent stops cleanly — no further writes, no further API calls, no further side effects. The agent reports the halt and exits. The operator updates a single file to take down the entire stack.

This sounds heavy-handed until you have watched an agent enter a tight loop that issues writes faster than you can revoke its credentials. The killswitch is the lower bound on damage. Without it, the operator's mitigation is racing the agent: kill the process, revoke the API key, undo the writes from git history, hope nothing destructive escaped to a downstream system. With it, the operator types one line and every agent in the stack stops on its next read.

## In practice

The vault includes a file at a known path — the convention used in this framework is `00-meta/killswitch.md` — whose contents specify the operational state of the agent stack. Under normal operation, the file says `STATUS: ACTIVE` and agents proceed. When the operator needs to halt everything, the file is updated to `STATUS: HALT` with a timestamp and a one-line reason. Agents poll this file as the first step of every non-trivial action; on seeing `HALT`, they record the halt in their own logs and exit cleanly.

Recovery is the reverse: investigate, fix the underlying issue, update the killswitch back to `STATUS: ACTIVE` with a note recording what was halted, what was found, and what changed. The killswitch file's history (in git) becomes a parallel incident log — every halt is captured in version control alongside the rest of the vault.

The killswitch is not a substitute for credential revocation, rate-limiting, or scoped permissions. It complements them. It is the brake the operator can reach without authentication, without admin consoles, without remembering which API key belongs to which agent. One file, one edit, one git commit. Done.

## Related

- [`01-orchestrator-principle.md`](01-orchestrator-principle.md) — the killswitch is the orchestrator's ultimate veto. Without it, the orchestrator/agent boundary collapses the moment an agent goes off the rails.
