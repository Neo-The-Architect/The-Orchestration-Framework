# 7. The Fundamentals Discipline

> **One-line statement:** Foundational engineering knowledge applied with rigor is what separates a durable AI-native operation from latest-repo / latest-tool / latest-MCP noise.

The faster the AI capability surface evolves, the more durable the foundational engineering disciplines underneath it become. Trends churn quarterly. Fundamentals do not. An operator who chases the latest framework, the latest agent pattern, the latest MCP integration, optimizes for the visible surface — and lands on a substrate that breaks every time the surface shifts. An operator who grounds in foundational engineering disciplines optimizes for the layer underneath that surface — and lands on a substrate that absorbs change rather than being broken by it.

## The disciplines we ground in

Not all are mastered. None are optional.

- **AI/ML engineering** — model selection, fine-tuning posture, evaluation methodology, deployment economics.
- **Computer intelligence** — algorithmic foundations, computational complexity, what's tractable and what's not.
- **AI intelligence** — capability and limit of current frontier models, prompting as engineering, agentic patterns.
- **Business intellect** — unit economics, pricing, revenue model design, distribution, compounding-vs-extracting business shapes.
- **Operating systems** — process, memory, file system, networking, security primitives. The substrate every AI tool eventually depends on.
- **RAG retrieval systems** — embedding quality, chunking strategy, retrieval evaluation, hybrid search, citations.
- **Systematic architecture design and development** — how systems are decomposed, how interfaces are designed, how scale is anticipated.
- **Agentic AI** — multi-agent coordination, tool calling, orchestration patterns, failure modes.
- **Generative AI** — generation patterns beyond chat (code, structured output, multimodal, planning).
- **Enterprise cloud development** — multi-region, multi-tenant, isolation patterns, compliance scaffolding.

## How the discipline shows up in the framework

The vault's `00-meta/` and `01-permanent/` directories are where fundamentals live. The operator deposits readings, ADRs, working notes, and reusable patterns indexed under these disciplines. Agents reference them when reasoning about new capabilities. New tools and frameworks pass through the lens of "which fundamental does this implement, and is the implementation sound?" before adoption.

This is the difference between an operator who runs an agentic CLI and an operator who builds a system *with* an agentic CLI. The first sees a tool. The second sees a layer that happens to be made of generated code, evaluable against known fundamentals.

## Cross-links

- [Decisions Are First-Class Objects](05-decisions-as-artifacts.md) — fundamentals discipline produces decisions; decisions land as artifacts.
- [Files Over Memory](02-files-over-memory.md) — fundamentals deposits in the vault; memory is the convenience layer over them.
- [Architecture: Knowledge Architecture as Compounding Infrastructure](../architecture/knowledge-architecture-as-compounding-infrastructure.md) — the architectural mechanism by which fundamentals compound across engagements.
