# Vault Structure

The vault is organized as ten numbered directories, each with a single well-defined purpose. The numeric prefixes enforce display order in any file browser and signal stability — once assigned, prefixes never change. Adopters preserve these names and purposes as-is.

| Directory | Purpose |
| --- | --- |
| `00-meta/` | System files. Agent configuration (CLAUDE.md and equivalents), skill definitions, templates, the killswitch file. Never edited manually during normal operation. |
| `01-permanent/` | Identity, principles, the operator's goals, personal systems, key facts. The slow-changing constitution. |
| `02-active/` | Current sprint, this week's focus, active tasks, kill list, not-doing list. Updated daily. |
| `03-ideas/` | The Idea Bank — business ideas, content concepts, system sparks, graveyard. Reviewed weekly. |
| `04-decisions/` | The decision log. One file per decision. Date-stamped. Append-only — superseded by new entries, never edited in place. |
| `05-research/` | Research artifacts, web clippings, deep-research outputs, briefings produced for or by the agent stack. |
| `06-infrastructure/` | VPS state, service inventory, runbooks, secrets index (names only, never values). |
| `07-content/` | Content calendar, hook bank, pillar definitions, performance log, captions. |
| `08-projects/` | Per-project working directories. One subfolder per active project. Project-internal organization is at the operator's discretion. |
| `09-journal/` | Daily notes, raw brain dumps before processing, voice transcription inbox. |

## Why ten

Ten is enough to separate concerns that would otherwise contaminate each other (decisions from research, ideas from active work, infrastructure from content) without proliferating into a directory tree so deep that retrieval becomes a navigation puzzle. Adopters who feel pressure to add an eleventh directory should first ask whether the candidate content fits a leaf inside an existing one. In the framework's experience, the answer is almost always yes.

## What does not belong in the vault

- Binary assets that bloat the git history (large images, video, datasets). Use a separate object store and reference by URL or content hash.
- Secrets in their cleartext form. The `06-infrastructure/secrets-index.md` records *which* secrets exist and *where they live*; the values themselves live in a secret store outside the vault.
- Anything you would be uncomfortable with an agent reading. The vault is read by every agent in the stack; if a piece of content needs different access controls, it does not belong here.

## Cross-references

- The numeric prefixes correspond directly to template directories under [`../templates/`](../templates/) — for each `NN-name/` here, there is a `templates/NN-name/` README explaining what to put there and how.
- The permissions for each directory are specified in [`permissions-table.md`](permissions-table.md) — the table makes the read/write boundaries explicit across the operator and the agent stack.
