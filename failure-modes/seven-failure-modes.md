# The Seven Failure Modes

Every framework fails. The question is whether failure is observable and recoverable. Below are the seven failure modes the Orchestration Framework anticipates, with the symptoms each produces and the countermeasure each requires.

| # | Failure Mode | What it looks like |
| --- | --- | --- |
| 1 | [Cathedral Drift](#1-cathedral-drift) | The framework grows more complex than the work it serves |
| 2 | [Specialist Creep](#2-specialist-creep) | Specialist verbs accumulate in the operator's active sprint |
| 3 | [Idea Bank Bloat](#3-idea-bank-bloat) | Ideas accumulate without triage |
| 4 | [Naming Paralysis](#4-naming-paralysis) | The operator stalls on a name and stops shipping |
| 5 | [Memory Drift](#5-memory-drift) | An agent's memory contradicts the vault |
| 6 | [Agent Runaway](#6-agent-runaway) | An agent loops or makes destructive edits |
| 7 | [Cross-Project Bleed](#7-cross-project-bleed) | Work from one project pollutes another |

---

## 1. Cathedral Drift

**Symptom.** The framework starts as a tool for shipping work. Over time, the framework itself becomes the work — operators spend more time maintaining the vault, refining their skills, tweaking the rhythms, than they spend on the goals the framework was supposed to serve.

**How it manifests.** New directories that hold three files apiece. Skills that have been invoked twice. Trigger words the operator never types. Weekly reviews that take 90 minutes because the vault has too much to walk. An apology in the operator's mouth when describing their workflow.

**Countermeasure.** The [monthly system audit](../rhythms/monthly.md), with explicit permission — and active expectation — to *delete* components. If the audit is not producing deletions, the audit is not working. The framework's posture is that components must justify their continued presence; the audit is the moment that justification gets demanded. See also: [philosophy 4 — token efficiency](../philosophy/04-token-efficiency.md), which is the same principle applied at the file level.

## 2. Specialist Creep

**Symptom.** The operator's active sprint accumulates verbs that begin with *write*, *code*, *design*, *record*, or *edit*. The orchestrator is doing specialist work, which means an agent or specialist is not being used where it should be — or the operator is reaching for the keyboard out of habit.

**How it manifests.** "Write the blog post" appears in the sprint instead of "approve the blog post draft from the agent." "Refactor the deploy script" instead of "review and merge the deploy-script refactor PR." The work still gets done, but the operator is in the wrong role for it, and over weeks the orchestration discipline erodes.

**Countermeasure.** A skill or convention the agent stack runs at vault-write time that flags non-orchestrator verbs in the active sprint. The flag is a soft prompt — *"this looks like specialist work, do you want to delegate it?"* — not a hard reject. The operator can override with a one-line note explaining why this instance is genuinely operator-bound. See also: [philosophy 1 — the orchestrator principle](../philosophy/01-orchestrator-principle.md).

## 3. Idea Bank Bloat

**Symptom.** `03-ideas/` has grown to dozens or hundreds of entries. New ideas no longer feel valuable to capture because they will be lost in the pile. Old ideas have not been revisited in months. The Idea Bank has become a graveyard with delusions of grandeur.

**How it manifests.** The operator stops dropping captures into `03-ideas/` because "it's already a mess." Or the operator captures faithfully but never triages, so the bank grows linearly with no decay. Either way, the idea layer stops doing the job the framework's [three-layers-of-state](../philosophy/03-three-layers-of-state.md) principle assigned to it.

**Countermeasure.** A hard cap of 15 active items in the Idea Bank. The 16th capture forces a triage: promote one (to `02-active/`), drop several, or update older entries to consolidate. The cap is not the point — the *forced triage* is the point. The cap is what triggers the triage automatically.

## 4. Naming Paralysis

**Symptom.** The operator has a clear idea of what to build, but stalls on what to call it. The project sits in `08-projects/untitled/` for days. Or it gets a placeholder name that nobody — including the operator — believes in, which itself becomes a reason to delay shipping.

**How it manifests.** A new project enters the framework and there is no working name. The operator opens a chat to brainstorm names. The brainstorm produces six options, none decisively better. The operator decides to "sleep on it." The project is on hold.

**Countermeasure.** A working name is mandatory at project creation. The first acceptable candidate becomes the working name. Names are decisions, and decisions are revisable — when a better name appears later, write a decision artifact recording the rename and execute it. The cost of working under a placeholder name is small; the cost of stalling on naming is large. The framework's bias is unambiguously toward shipping under an okay name.

## 5. Memory Drift

**Symptom.** An agent's memory contains assertions that contradict the vault. The agent reasons from memory, produces output, and the output disagrees with the canonical state on disk.

**How it manifests.** An agent says "the operator's current sprint includes X" when X was killed two weeks ago. Or the agent applies a rule from a constitution that has since been amended. Both happen because agent memory is opaque to the operator and slow to update.

**Countermeasure.** The [files-over-memory](../philosophy/02-files-over-memory.md) principle is explicit: when memory and the vault disagree, the vault wins. Operationally, this means agents are configured to read the relevant vault state at the start of each material action, and to treat their own memory as a cache that may be stale. The countermeasure is architectural — agents that consult the vault rather than rely on memory do not produce drift in the first place.

## 6. Agent Runaway

**Symptom.** An agent enters a tight loop, makes destructive edits, or otherwise behaves outside its expected envelope. Without intervention, it would continue until its credentials are revoked or its process is killed.

**How it manifests.** A misconfigured runbook iterates over the wrong directory. A retry loop on a flaky API spawns a thousand requests in a minute. A long-running agent gets a malformed prompt and starts rewriting files with garbage. The longer the runaway runs, the more there is to undo.

**Countermeasure.** The [killswitch](../philosophy/06-killswitch.md). Every agent in the stack reads the killswitch file at the start of every non-trivial action; on `STATUS: HALT`, the agent stops cleanly and exits. Combined with git as the rollback substrate, the killswitch puts a lower bound on the damage an agent can do — finite damage, recoverable from version control. The killswitch is not a substitute for credential scoping or rate-limiting, but it is the last-line brake the operator can reach without admin consoles or per-agent credential revocation.

## 7. Cross-Project Bleed

**Symptom.** Work from one project pollutes another. Notes that belong to project A end up in project B's directory. Decisions made for project A get treated as universal. Skills written for project A's specifics get applied to project B with bad results.

**How it manifests.** The operator is working in two projects simultaneously and an agent reads from the wrong project's context. Or a "general" file in `01-permanent/` is actually a project A artifact that happened to be saved at the top level. Or a runbook written for project A's deploy gets invoked during project B's deploy without being revised.

**Countermeasure.** Per-project working directories under `08-projects/`. Project-specific state lives inside the project directory, not at the top level of the vault. Shared context — actual cross-project principles, not project A masquerading as universal — lives in `01-permanent/` and is read-only to projects. The directory boundary is the discipline; the operator's job is to resist the temptation to "hoist" project-specific content into the permanent layer prematurely.
