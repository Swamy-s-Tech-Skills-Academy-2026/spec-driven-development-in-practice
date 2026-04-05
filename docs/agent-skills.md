# Agent skills in this repository

Bundled procedures live under `.github/skills/` as `SKILL.md` files (YAML frontmatter + Markdown body). The same tree is mirrored at `.cursor/skills/`; parity is checked in CI when those paths change.

## Why skills exist

Skills give assistants **progressive disclosure**: match a task to a small bundle instead of loading every rule file. They complement `CLAUDE.md`, `.cursor/rules/*.mdc`, and `.github/copilot-instructions.md`.

## Bundles (high level)

| Skill folder | Use when |
|--------------|----------|
| `sdd-learning` | Editing topic Markdown — scope, voice, zero-copy, SDD topic map |
| `topic-units` | Adding topics — on-demand folders, `NN_<slug>.md` naming |
| `ci-checks` | Running markdownlint (and optional Lychee) like CI |
| `docs-verification` | Auditing structure and internal links |
| `workspace-review` | Full repo health pass |
| `e2e-testing` | Smoke documentation checks |

## Canonical reference

See `.github/skills/README.md` for the parity verification script and the authoritative list of bundles.
