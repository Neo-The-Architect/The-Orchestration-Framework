# 2. Files Over Memory

> If the file does not exist, the knowledge does not exist.

AI memory systems are opaque, lossy, and bound to a single platform. They cannot be grepped, version-controlled, audited, or migrated. They die when a vendor changes a policy.

The Orchestration Framework treats files as the canonical state of the operator's reality. Markdown files in a structured vault represent identity, decisions, infrastructure, ideas, and active work. AI memory is a convenience layer on top of files — never a replacement for them. When agent memory and the vault disagree, the vault wins. Always. Without exception.

This is the sovereignty principle applied to cognition. Memory you cannot inspect is memory you do not control. Memory you cannot version is memory you cannot trust. Memory you cannot move is memory that holds you hostage to a vendor's roadmap. Files solve all three problems and add a fourth benefit: every agent in the stack can read them, including agents that did not exist when the file was written.

## In practice

A vendor updates the memory policy on the operator's primary AI assistant. Conversations from six months ago are no longer recallable. Without files, the operator must reconstruct the context from screenshots, exports, or memory. With files, the relevant decisions, briefs, and project state are still on disk, still in git, still readable by any AI assistant the operator points at the vault. The vendor's policy change becomes a logistical inconvenience, not a knowledge-loss event.

The same pattern holds for migration. If the operator decides to switch to a different agentic AI tool, the new tool reads the same vault. No re-onboarding, no re-explaining, no rebuilding of context. The vault is the operator's continuity layer across vendors.

## Related

- [`05-decisions-as-artifacts.md`](05-decisions-as-artifacts.md) — decisions are the highest-value case of file-over-memory. A decision captured only in chat is a decision that will be re-litigated when the chat scrolls off.
