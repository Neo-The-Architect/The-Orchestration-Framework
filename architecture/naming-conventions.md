# Naming Conventions

Naming is a small thing that compounds. A vault that mixes `MyTask.md` with `my-task.md` with `My_Task.md` becomes a vault where retrieval is unreliable and grep produces noise. The conventions below are deliberately narrow — they cost nothing to follow and they pay off every time an agent searches the vault.

## Rules

- **Directory prefixes.** The ten top-level directories use a numeric prefix (`00-`, `01-`, … `09-`) to enforce display order. Prefixes are reserved — once assigned, they do not change. Sub-directories inside `08-projects/` and `05-research/` may use prefixes if it helps display order, but it is not required.

- **File names: lowercase, hyphen-separated.** No spaces. No camelCase. No underscores in routine file names. `decision-postgres-single-instance.md` not `Decision_Postgres_SingleInstance.md` or `decisionPostgresSingleInstance.md`.

- **Date prefixes for time-anchored files.** Decision and journal files are date-prefixed in ISO format: `2026-04-29-decision-slug.md` and `2026-04-29-journal.md`. The date comes first so chronological sort in any file browser is automatic.

- **Templates live in `00-meta/templates/` and are copied, not edited in place.** When you instantiate a template, copy it to its target location and rename it; never let the template file itself drift, because every other adopter (including future-you starting a new vault) depends on the template being clean.

- **Active files have stable names; archived versions get suffixes.** When a file is superseded — say a sprint plan rolls over — the new file takes the canonical name and the old one is archived with a date suffix (`sprint-2026-w16.md`) inside the appropriate sub-directory. Never let two files compete for the same canonical name.

## Why this matters

Agents grep the vault. Consistent naming means an agent looking for "the current sprint" reaches `02-active/sprint.md` reliably rather than guessing between three near-identical files. Inconsistent naming forces every agent (and every prompt) to enumerate alternatives, which costs tokens, costs latency, and produces flaky behavior at scale.

The same logic applies to the operator. Predictable names mean predictable retrieval. The five seconds saved per lookup, multiplied by every interaction with the vault, is a meaningful fraction of the operator's daily attention.
