---
name: github-repo-skill-template
description: "Template for creating new Agent Skills intended to be hosted and versioned in a GitHub repository. Use when initializing a skill for GitHub, setting up skill repo structure, or bootstrapping a skill project that will be marked as a GitHub template repository. Incorporates AFGS-compatible governance boundaries so generated skills do not self-authorize material decisions."
---

# GitHub Repo Skill Template

This directory serves two related but distinct purposes. Keep them separate in practice.

1. **GitHub Repository Template** — a starter repository that users copy (via GitHub's "Use this template" feature) to create a new skill.
2. **Agent Skill** — instructions an AI agent can follow to help initialize, customize, and validate a new skill repository.

Do not treat the current contents as a finished production skill. The scripts/, references/, and assets/ directories contain explicit placeholders only.

## When to Use (as Agent Skill)

- A user wants to start a new skill that will live in its own GitHub repository.
- A user needs the minimal valid Agent Skills layout plus repository-level files suitable for public reuse.
- A user asks to turn an existing skill directory into a GitHub template repository.
- The skill being created may later be used in domains that involve material decisions (capital, binding commitment, regulatory exposure, control change). In that case apply the governance boundaries below before finalizing.

## Governance & Authority Boundaries (AFGS-compatible)

This template embeds prior-art governance patterns so that skills produced from it do not accidentally create authority.

Hard constraints (non-negotiable):

- The skill being created, and this template skill itself, create no organizational, legal, financial, or execution authority.
- Analysis, structure, or draft language never equals permission to act, bind, publish, or execute.
- If the request involves capital allocation, binding legal commitment, high-impact procurement, project finance, concession, long-term contract, license-to-operate exposure, fundraising, change in control, or clear downside/irreversibility, the final path must pass through a materiality gate equivalent to `mdgr-core`. This template skill does not perform that gate; it only flags the need and stops short of any verdict.
- Domain specialists or production skills remain analytical only. They never issue PERMIT, HOLD, BLOCK, or execution eligibility.
- Copy or narrative that will be published, submitted, or used as investor/public material with factual, legal, or reputational claims requires a separate release-gate review. This template does not own that gate.
- Urgency, multi-domain complexity, or user insistence does not bypass the materiality check.
- Output must distinguish formal position, practical enforcement, and residual risk. Do not invent certainty.
- Current capability level is SC1-capable only. Never claim external registry binding, atomic execution control, or self-sufficient governance authority.

When materiality signals exist, state the routing line explicitly, produce structured findings only, and hand off. Do not soften or convert findings into an execution recommendation.

See `references/governance-principles.md` for the compact principle set.

## Core Workflow

1. Copy or use this repository as a GitHub template and rename the root directory to the target skill name (must match the `name` field in SKILL.md).
2. Edit the YAML frontmatter in SKILL.md: set only `name` and `description`. Remove any non-standard fields.
3. Perform a materiality check on the intended use of the new skill. If material signals exist, note them and require hand-off to an appropriate decision gate before the skill is treated as production-ready. Do not issue any verdict.
4. Replace the body of SKILL.md with the actual instructions for the new skill. Keep it concise. Move detailed material to references/ only if needed. Embed the same no-authority constraints if the skill will operate in material domains.
5. Update CHANGELOG.md.
6. Add or remove content in scripts/, references/, or assets/ as required by the new skill. These directories are optional.
7. Replace the example cases in evals/ if you choose to keep evaluation files.
8. Validate with a portable command (see Validation below).
9. Commit and, if desired, mark the repository as a Template Repository on GitHub.

## Validation

Use a standard-compatible validator when available:

```bash
skills-ref validate .
```

The reference validator is a demonstration implementation. It does not guarantee production readiness. Always review the output and the skill contents manually. Validation of structure does not confer authority or execution eligibility.

## Repository Conventions

- For a single-skill repository the skill directory is the repository root. A README.md at the root is expected and useful.
- scripts/, references/, and assets/ are optional. Do not add them unless they serve a concrete purpose.
- Prefer imperative voice in SKILL.md instructions.
- Keep SKILL.md focused on what the agent must do. Put human-facing documentation in README.md.
- Governance boundaries travel with the skill. Do not strip them when the skill is copied into a new repository.

## Customization Checklist

- [ ] `name` in frontmatter matches the directory name
- [ ] `description` is a single clear sentence that states purpose and trigger conditions
- [ ] No non-standard frontmatter fields remain
- [ ] Body contains concrete steps
- [ ] Materiality signals (if any) are flagged and hand-off is stated
- [ ] No-authority constraints are present when the skill may touch material domains
- [ ] Placeholder files in scripts/, references/, assets/ have been replaced or deleted
- [ ] README.md and LICENSE exist at repository root
- [ ] Validation command succeeds (or known limitations are documented)
- [ ] Repository is committed and, if intended, marked as a Template Repository

## Resources

The files under scripts/, references/, and assets/ are placeholders. They exist only to show possible layout. Delete or replace them before treating the skill as ready for use.

`references/governance-principles.md` contains the compact AFGS-compatible principle set used by this template.
