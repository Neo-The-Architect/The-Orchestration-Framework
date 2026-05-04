# Architecture

The vault is the physical embodiment of the [philosophy](../philosophy/). It lives on the operator's primary device, syncs to a hardened VPS over a mesh networking layer, and is version-controlled with git. Every directory has a single, well-defined purpose. No directory may overlap with another.

This section captures the canonical architecture. Adopters preserve the directory names, the naming conventions, and the permissions structure as specified — these are the parts of the framework that are deliberately rigid, because their rigidity is what makes them legible to every agent that reads the vault.

| File | What's in it |
| --- | --- |
| [`vault-structure.md`](vault-structure.md) | The ten numbered directories, their purposes, and what does and does not belong in each |
| [`naming-conventions.md`](naming-conventions.md) | File and directory naming rules — prefixes, casing, date formats, template handling |
| [`permissions-table.md`](permissions-table.md) | Read / write permissions across the operator and the agent stack, with the three constrained protocols (propose-only, append-only, R/W) explained |
| [`security-layer-for-foreign-code.md`](security-layer-for-foreign-code.md) | The verification gate every external repo, MCP, skill, or connector passes through before entering the substrate |
| [`knowledge-architecture-as-compounding-infrastructure.md`](knowledge-architecture-as-compounding-infrastructure.md) | Why the vault is a compounding asset, not storage — the mechanism by which operator learning compounds across engagements |
| [`anonymization-protocol-for-public-artifacts.md`](anonymization-protocol-for-public-artifacts.md) | Locked verification language and corrective procedures that keep the operator's private exclusion list out of public-facing content |

Customization is permitted at the leaves (project subfolders, journal sub-organization, content-pillar names) but not at the trunk (the ten numbered directories, their prefixes, their permissions). Operators who change the trunk are building a different framework, and that is fine — but it is no longer this one, and the cross-links and conventions in the rest of this repo will not apply cleanly.
