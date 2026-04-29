# 05-research/

## Purpose

Research artifacts. Web clippings, deep-research outputs, briefings produced for or by the agent stack, summaries of long-form material, reference notes from books and articles.

This directory is the operator's external knowledge corpus. The Strategic Counsel reads from it during brainstorming. The Autonomous Operator may add to it through scheduled research tasks. The operator drops things in continuously and revisits selectively.

## What goes here

- **Topic briefs.** Short-form summaries of a topic the operator has researched, with citations. Useful when the same topic recurs across projects.
- **Web clippings.** Excerpts from articles, blog posts, papers — the operator's external memory for content they want to reference later.
- **Deep-research outputs.** Reports produced by research-specialist tools, with the operator's annotations.
- **Book and article notes.** Distilled takeaways from long-form material. Distillation discipline applies — see [philosophy 4 — token efficiency](../../philosophy/04-token-efficiency.md).
- **Briefings prepared for specific decisions or projects.** Cross-link to the relevant decision file or project directory.

## What does not go here

- **The operator's own original thinking** (that goes in `09-journal/` or `08-projects/<project>/`).
- **Project-specific research that only matters to one project** (lives inside the project directory).
- **Raw data dumps** that are too large for git or never get read again. Use external storage; reference here.

## Structure

The framework does not prescribe internal structure for `05-research/`. Common patterns adopters use:

- Flat by topic: `auth-patterns.md`, `serverless-trade-offs.md`, etc.
- Nested by domain: `engineering/`, `marketing/`, `business-models/`, with files inside.
- Date-prefixed by capture date when the temporal context matters.

Pick a structure, stick with it for a few months, refine if and when the structure is failing the retrieval pattern.

## Update cadence

Continuously. Research is captured as it is encountered.

## Permissions

| Actor | Access |
| --- | --- |
| Operator | R/W |
| Local AI agent | R/W |
| Chat AI assistant | R/W |

All actors have full access. Research is the most permission-permissive directory because the cost of an erroneous write is recoverable (the original source still exists), the value of agent contributions is high (agents are good at summarization and extraction), and the audit-trail concerns that govern other directories do not apply.
