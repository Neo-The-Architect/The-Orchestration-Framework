# Templates

This directory holds skeleton files for adopters to instantiate in their own private vaults. The templates correspond directly to the [vault structure](../architecture/vault-structure.md) — each numbered subdirectory here mirrors the same number in the canonical vault layout.

**Read this carefully:** the templates are *not* meant to be filled in inside this repo. This repo is methodology and reference. The Template Repository feature is intentionally disabled in GitHub. Your private vault — the one that holds your decisions, your active sprint, your journal — lives on your own machine, in your own private repository, and never touches this public repo.

## Adoption sequence

1. **Read [`philosophy/`](../philosophy/) and [`architecture/`](../architecture/) first.** Without the philosophical context, the template structure reads as arbitrary. The directories are shaped the way they are because of the principles in `philosophy/`; the conventions are what they are because of the rationale in `architecture/`. If you skip both, you will discard the parts that look optional, and the parts you discard are usually doing the actual work.

2. **Decide which directories to start with.** A minimal first instantiation is `01-permanent/`, `02-active/`, `03-ideas/`, and `09-journal/`. That is enough to begin running the [daily](../rhythms/daily.md) and [weekly](../rhythms/weekly.md) rhythms against. The other directories can be added as the work calls for them — `04-decisions/` once the first non-trivial decision is on the table, `08-projects/` once a discrete project exists, and so on.

3. **Copy the templates into your own private vault.** Initialize a private repository on your own machine. Copy the directories you decided to start with from this repo's `templates/` directory into the root of your private vault, dropping the `templates/` prefix. Rename `.template` files to remove the suffix as you instantiate them.

## What is and isn't here

Each numbered subdirectory in `templates/` contains a README that explains the purpose of that directory, what kinds of files go in it, the expected update cadence, and the read/write permissions for each actor in the agent stack. Three subdirectories also contain actual template files:

| Subdirectory | Has template file? | What |
| --- | --- | --- |
| `00-meta/` | Yes | `killswitch.md.template` — the killswitch file every agent reads before acting |
| `04-decisions/` | Yes | `decision-template.md` — the decision-artifact skeleton |
| `09-journal/` | Yes | `daily-journal-template.md` — daily entry skeleton |

The other subdirectories (`01-permanent/`, `02-active/`, `03-ideas/`, `05-research/`, `06-infrastructure/`, `07-content/`, `08-projects/`) ship with READMEs only. The files inside those directories are too operator-specific for a useful skeleton — the framework specifies the *purpose* of the directory, but the structure of the files inside is a leaf decision the adopter makes.

## What this directory is not

- *A starter kit you fork.* Forking this repo and working in it directly is the wrong adoption pattern. Your private state belongs in your own private vault, not in a public fork.
- *An exhaustive set of pre-built skills, prompts, or runbooks.* The framework specifies the architecture, not a runtime. Adopters write their own skills and runbooks against the vault structure, informed by the philosophy.
- *A guarantee that every adopter's vault will look identical.* Beyond the trunk (the ten numbered directories, the naming conventions, the permissions table), customization is welcome at the leaves. Two adopters running the framework correctly may have very different content layouts inside `08-projects/` or `07-content/`.
