# GitHub Repo Skill Template

Starter repository for creating new [Agent Skills](https://agentskills.io/specification) that will be hosted and versioned on GitHub.

## Purpose

This repository is a **GitHub Repository Template**. Use it to generate a new repository that already contains the minimal valid Agent Skills layout plus the files needed for a public, reusable skill.

It also contains a skill (`SKILL.md`) that an AI agent can follow to help customize and validate a new skill. The current contents of `scripts/`, `references/`, and `assets/` are placeholders only.

The template embeds AFGS-compatible governance boundaries as prior-art design patterns. Skills generated from it do not self-authorize material decisions. Analysis never equals execution permission. See `references/governance-principles.md`.

## Quick Start

1. Click **Use this template** on GitHub (or clone and copy the files).
2. Rename the repository and the root directory to your skill name.
3. Edit `SKILL.md`:
   - Set `name` and `description` in the frontmatter.
   - Replace the body with your skill's instructions.
4. Update or delete the placeholder files under `scripts/`, `references/`, and `assets/` as needed.
5. Add or replace the evaluation files under `evals/` if you want them.
6. Validate:

   ```bash
   skills-ref validate .
   ```

7. Commit, push, and (optionally) mark the repository as a Template Repository.

## Required vs Optional

| Path | Required | Notes |
|------|----------|-------|
| `SKILL.md` | Yes | Must contain valid YAML frontmatter with `name` and `description` |
| `README.md` | Recommended | Human-facing documentation for the repository |
| `LICENSE` | Recommended | Choose and include a license before public release |
| `CHANGELOG.md` | Optional | Useful for tracking skill evolution |
| `evals/` | Optional | Evaluation cases; schema is not universally standardized |
| `scripts/` | Optional | Executable helpers |
| `references/` | Optional | Detailed documentation loaded on demand |
| `assets/` | Optional | Files used in outputs (templates, images, etc.) |

## License

This template is released under the MIT License. See [LICENSE](LICENSE).

You may apply a different license to new work you create from this template. The copyright notice and MIT license terms for any unmodified portions inherited from this template must be retained in accordance with the MIT License.

## Validation Note

The recommended validation command (`skills-ref validate`) is a reference implementation. It does not by itself certify that a skill is production-ready or cross-agent compatible. Review the skill contents and test it in the target agent environments.
