# Security Layer for Foreign Code

Before any external repository, software package, MCP server, agent skill, or third-party connector enters the operator's substrate, it passes through a verification layer. This is not optional best practice. It is non-negotiable architectural discipline for any operator running an agentic stack against real data.

## Why this layer exists

Frontier AI shifts the trust topology of code. Code generation is commoditizing. Trust in code is not. The faster code can be authored or adopted, the more important the verification gate becomes. An operator who adopts third-party MCPs at the speed of release will eventually adopt one that is hostile, compromised, or unsafe by accident. An operator who runs every adoption through a gate may move slightly slower but remains operationally sovereign.

The Orchestration Framework treats the operator as the unique unit of trust. Every layer of the architecture is designed to keep that trust under operator control. A foreign-code gate is the natural extension: an explicit policy on what may enter the substrate, applied uniformly so the operator does not re-decide per adoption.

## What the gate does

| Stage | What it checks |
| --- | --- |
| Intake | Declared component metadata: name, version, source, declared permissions, declared dependencies. |
| Static scan | File and code analysis (signature checks, known-bad-pattern detection, secret scanning). |
| Dependency provenance | Recursive supply-chain check on declared dependencies (registry origin, signature, age, maintenance signal). |
| Permission diff | Required permissions discovered through static analysis vs declared permissions in metadata. Mismatch is a failure. |
| Sandbox execution (where applicable) | Run in an isolated environment; observe network, file system, and process behavior. |
| Verdict artifact | A signed verdict file persisted to the vault under the decisions layer. Either CLEARED, BLOCKED, or CLEARED-WITH-CONDITIONS. |

The verdict is durable: future references to the same component (same version, same source) reuse the verdict rather than re-running the gate. New versions trigger a fresh gate run.

## What the gate does not do

This layer governs what enters the substrate at adoption time. It does not govern what AI agents do at runtime. Runtime governance — pre-execution policy checks, runtime verification, audit log generation — is a separate concern, often implemented as a complementary trust layer that sits between agents and the systems they touch.

The two are complementary. Adoption-time gating reduces the attack surface that runtime governance must defend.

## Allowlist and grandfathering

A pure gate-everything posture is impractical for operators with existing substrates. The pragmatic posture: maintain an allowlist of components grandfathered as of the moment the gate goes live, plus components manually verified during the migration window. Future adoptions go through the gate. Grandfathered components are migrated to verified status as a deliberate, paced workstream rather than as a bottleneck.

## Where the gate lives in the vault

Verdict artifacts persist under `04-decisions/foreign-code-verifications/<component>-<version>.md`. Allowlist persists at the architectural seam where the substrate's adoption policy lives — typically a single file under the operator's repo, referenced by every runbook that adopts new code.

## Cross-links

- [Decisions Are First-Class Objects](../philosophy/05-decisions-as-artifacts.md) — verdicts are decisions; they land as artifacts, not chat messages.
- [The Killswitch Is Sacred](../philosophy/06-killswitch.md) — a BLOCKED verdict is a killswitch invocation in miniature. The operator must always be able to refuse.
- [Permissions Table](permissions-table.md) — declared permissions in component metadata are checked against required permissions in the same way the permissions table governs agent reads and writes.
