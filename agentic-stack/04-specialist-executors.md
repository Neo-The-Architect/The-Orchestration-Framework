# Specialist Executors

> Single-purpose agents and connectors. Deterministic tasks where a specialist tool outperforms a generalist agent.

The Specialist Executor role covers everything that is not a general-purpose AI agent: connector-based services (email, calendar, document storage, content scheduling), media-production tools (text-to-speech, video generation), and any narrow, well-bounded API the operator wires into the stack.

These are not part of the AI agent stack proper. They are the executors that the AI agents — Strategic Counsel, Tactical Builder, Autonomous Operator — reach for when a task is best served by a deterministic tool rather than another round of model inference.

## Privileges

- Each specialist has its own scope, defined by the connector's permissions or the API key's grants.
- Specialists do not write directly to the vault except where explicitly configured (e.g., a transcription service depositing into `09-journal/inbox/`).
- Credentials are stored outside the vault. The vault holds only references.

## Categories

- **Communication specialists.** Email drafting and sending, calendar block creation, scheduling links. Reached via connector protocols (MCP, native integrations) or direct API.
- **Storage specialists.** Document repositories, object stores, version-controlled archives. Used to hold artifacts that do not belong in the vault (large binaries, shared documents, content awaiting publication).
- **Research specialists.** Notebook-style research tools, web-fetch services, document-summarization APIs. Used by the Strategic Counsel to extend its working context with externally-sourced material.
- **Content scheduling specialists.** Platforms that hold a queue of content posts and publish on schedule. The vault holds the calendar and the captions; the specialist holds the queue.
- **Media-production specialists.** Text-to-speech, image generation, video assembly. Used to produce specific assets called for in content runbooks.

## When to invoke

A task should route to a specialist when *all three* of the following hold:

1. The task is well-specified — inputs and outputs are clear.
2. The task is deterministic — same inputs produce the same outputs reliably.
3. A purpose-built tool exists that does the task better, faster, or cheaper than a general-purpose AI agent could.

If any one of those is missing, the task probably belongs with one of the AI agent roles. In particular, "the same inputs produce the same outputs reliably" rules out tasks that need judgment — a specialist email-sender will send whatever it is told to send, including poorly-drafted email. Drafting belongs with the Strategic Counsel; sending belongs with the specialist.

## Why specialists are listed last

The framework lists specialists last because they are the leaves of the agent tree, not the trunk. The trunk is the three AI agent roles (Counsel, Builder, Operator) plus the operator at the root. Specialists are tools the trunk reaches for. Adopters who start by listing specialists ("first I need to wire up email, then calendar, then…") are building inside-out, and the result is usually a stack where the AI agents have nothing to coordinate because all the work has been pre-routed to specialists.

The right sequence is the other way around: get the AI agent stack working against the vault first, then add specialists as the stack identifies tasks where a deterministic tool would outperform another inference call.
