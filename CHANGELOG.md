# Changelog

## 2026-10-29
- Correction: the CI workflow described in the 2026-10-11 entries was not included in the published repository (no `.github/workflows/` directory). The repository description no longer claims CI checks. Restore the workflow before reinstating that claim.

## 2026-10-11
- Initial skill creation (skill-creator baseline)
- Targeted revision: removed non-standard frontmatter fields, made validation command portable, clarified dual purpose (GitHub template vs agent skill), added repository-level README and LICENSE guidance, marked resources as optional placeholders
- Governance integration: added AFGS-compatible authority boundaries, materiality flagging, hand-off rules, and `references/governance-principles.md` so the template qualifies as structured prior art without creating self-authority
- Closure fixes (v1.0): copyright holder filled in LICENSE, README link corrected to agentskills.io/specification, CI strengthened to enforce YAML delimiters, skill name rules, and description length limit
- Validation layer fix (v1.0): CI now installs and runs skills-ref as primary gate; additional checks enforce directory name match, no consecutive hyphens, full YAML parse (including duplicate keys and block scalars), and description length; README license note clarified to require retention of MIT notice on inherited portions
- Non-blocking closure (v1.0): corrected PyYAML duplicate-key comment; pinned skills-ref==0.1.1 and pyyaml==6.0.2; added setup-python 3.12 for reproducible CI
