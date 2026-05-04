# Anonymization Protocol for Public Artifacts

**Pattern: Public-private artifact separation requires explicit verification language that does not leak the exclusion list.**

Many operators run a hybrid workspace: public repositories for the methodology, the open-source code, the build-in-public artifacts; private vaults for client information, in-flight projects, brand identities not yet ready to be associated with the public work, and personal context. The boundary between the two is normally maintained by the operator's discipline. Discipline-by-vigilance is an unstable equilibrium: every contribution risks crossing the line, and over a long enough timeline at least one contribution will.

This protocol replaces vigilance with a structural rule.

## The rule

The operator maintains a private exclusion list — names of business entities, projects, and identities that must never appear in any public artifact. The list itself is private. It lives in the operator's vault, not in any public repository, not in any contribution guide, not in any verification note.

All public-facing content — pull request bodies, commit messages, issue bodies, file contents, decision artifacts, runbook text, README content, changelog entries — must never reference the exclusion list explicitly. Listing the strings in a verification note defeats the purpose of the verification.

## The verification language

Every anonymization grep check produces a single line of public-facing output:

> Anonymization grep clean — verified zero matches against canonical private-brand exclusion list at commit time. Operator maintains the canonical list privately.

This phrasing is locked. It does not name the strings, does not name the count, does not name the file paths inspected. It names only the fact of the check and where the canonical list lives. Operators adopting this protocol may adapt the phrasing to their voice but must preserve the property: the verification statement is non-revealing.

## How the grep is run

The grep command itself is run privately on the operator's machine or in ephemeral CI logs that are not committed to a public branch. The grep's pattern argument and any output that includes matched strings are never echoed into committed content. If a check needs to be reproducible across operators, the pattern lives in a `.gitignore`d file or an environment variable, never in a public README or workflow file.

## Failure modes and corrections

| Failure mode | Correction |
| --- | --- |
| Strings appear in a feature-branch commit message before merge | Force-push correction with `git push --force-with-lease` after `git commit --amend`. |
| Strings appear in a feature-branch PR body before merge | Edit the PR body via the platform's edit affordance; verify the surface is clean. |
| Strings appear after merge — branch already in `main` | Treat as a real disclosure event. Capture in postmortem template, escalate, prefer corrective commit with honest changelog note over silent rewrite of public history. The leak is durable; the response should be honest. |
| Strings appear in residual artifacts (issue bodies, comments, releases) | Edit each artifact through the platform; verify each surface; if the residual exposure window matters, close-and-reopen from a fresh branch. |

## Why the protocol exists

This pattern was crystallized in response to a real failure-mode that operators with hybrid public-private workspaces should expect to encounter at some point: the verification *language describing the check* leaks exactly what the check was meant to protect, because the operator (or the agent acting on the operator's behalf) wrote the exclusion list as part of the verification note. The grep ran correctly. The grep result was reported correctly in number-of-matches terms. But the prose around the result — the human-readable affordance — listed the strings the grep was searching for.

The structural correction is the locked verification language above. The grep stays correct. The prose around the result becomes uniform, non-revealing, and decoupled from the list's content.

## Cross-links

- [Files Over Memory](../philosophy/02-files-over-memory.md) — the exclusion list lives in files in the private vault, not in agent memory or chat context, so it survives session resets.
- [Decisions Are First-Class Objects](../philosophy/05-decisions-as-artifacts.md) — the policy decision behind the locked verification language is itself an artifact in the operator's decisions layer, with rollback conditions named.
- [Permissions Table](permissions-table.md) — the public/private boundary mirrors the read/write boundary between agents in the agentic stack. Agents that have access to the private vault must be configured not to surface its contents into the public surface.
- [Security Layer for Foreign Code](security-layer-for-foreign-code.md) — companion architectural primitive. Both protocols treat the operator's substrate boundary as load-bearing infrastructure that needs structural enforcement, not vigilance.
