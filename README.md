# The Orchestration Framework

> **Status:** v0.1 — public release. Methodology stable. Templates evolving.

<!-- TODO(philosophy commit): Replace this paragraph with the source-anchored "what this is" statement once the philosophy section lands. -->
The Orchestration Framework is a working methodology for operators who run their lives and businesses through a coordinated set of AI agents. It defines a vault architecture for state, a stack of agent roles with explicit responsibilities, daily and weekly rhythms that keep the system honest, and a small set of trigger words and failure modes that surface when the discipline slips. It is shared publicly so that other operators can read it, adapt it to their own context, and instantiate it in their own private vaults.

This is methodology and reference, not a starter kit. The Template Repository feature is intentionally disabled. You read the philosophy, you copy the template skeletons into your own private vault on your own machine, and you make the framework yours.

## Quick start

1. **Read the philosophy** — start with [`philosophy/`](philosophy/). The six foundational principles explain why the framework is shaped the way it is. Without them, the architecture and rhythms read as arbitrary rules.
2. **Review the architecture** — [`architecture/`](architecture/) defines the vault structure, naming conventions, and read/write permissions across the agent stack. This is the canonical part of the methodology that adopters preserve as-is.
3. **Instantiate the templates** — copy files from [`templates/`](templates/) into your own private vault. Do not fork this repo and work in it; the public repo is reference material, not a place for your data.

## Directory map

| Directory | What's in it |
| --- | --- |
| [`philosophy/`](philosophy/) | Six philosophical foundations the rest of the framework rests on |
| [`architecture/`](architecture/) | Vault structure, naming conventions, agent permissions table |
| [`agentic-stack/`](agentic-stack/) | The four agent roles and how information flows between them |
| [`rhythms/`](rhythms/) | Daily, weekly, and monthly operating rhythms |
| [`triggers/`](triggers/) | The three trigger words: GAMIFY, ORCHESTRATE, ITERATE |
| [`failure-modes/`](failure-modes/) | Seven recurring failure modes and their countermeasures |
| [`templates/`](templates/) | Skeleton files for adopters to copy into their own private vaults |

## License and contribution

Released under the [MIT License](LICENSE). See [CONTRIBUTING.md](CONTRIBUTING.md) for the (deliberately narrow) scope of welcome contributions and [CHANGELOG.md](CHANGELOG.md) for version history.
