# CLAUDE.md — Claude Code entry point

This file provides Claude Code with the essential context for working in this repository.
For full details, see the referenced files below.

## Repository

**Spec-Driven Development in Practice** — Swamy PKV's personal learning workspace for exploring
Spec-Driven Development (SDD) and deterministic AI system design. Markdown-first notes and experiments.
**Not** a web application or production system.

## Non-negotiable: Swamy only

This repository is **Swamy PKV's personal learning** material. It is **not** maintained for other
learners, employers, or the public. Do **not** reword `README.md`, reading notes, or docs to imply a
general audience (for example "students," "learners," "you" as a tutorial reader) unless Swamy
explicitly asks. Preserve the **Scope** block in `README.md`.

## Repository structure

Content is organized into topic folders created **on demand** — no pre-scaffolding. **Human-readable
layout** (same table as `.cursor/rules/09_week-companion-architecture.mdc`):

| Folder | Purpose |
|--------|---------|
| `notes/` | Theory, insights, and evolving understanding |
| `specs/` | Behavior specifications and prompt contracts |
| `evals/` | Evaluation strategies and eval loop designs |
| `patterns/` | SDD patterns and reusable practices |
| `experiments/` | Small experiments and iteration notes |
| `docs/` | Meta documentation and repository guides |

Topic files use **`NN_<slug>.md`** (two-digit prefix, kebab-case). Never `00_`.

**SSOT write-up**: `docs/01_repository-structure.md`
**Governance**: `.cursor/rules/09_week-companion-architecture.mdc`
**Naming**: `.cursor/rules/07_file-naming-conventions.mdc`

## Agent skills (`SKILL.md`)

Bundled on-demand procedures live under `.github/skills/` (mirrored at `.cursor/skills/`). They use YAML
frontmatter plus a Markdown body so agents can match tasks without loading everything up front. How that
complements `CLAUDE.md`, rules, and MCP: **`docs/agent-skills.md`**.

## Key rules

- **Zero-copy**: All public content must be original synthesis. No copy-paste from reference materials or external sources.
- **Voice**: First-person learning journey (Swamy's notes). Avoid instructor or "course" framing in reading notes.
- **Docs style**: Use `##` for main topics, `###` for subtopics. Comments in any incidental code explain *why* not *how*.

## Environment

No Python environment required — this is a Markdown-only learning repository.

## CI checks (run locally)

Aligned with `.github/workflows/ci-documentation.yml`. Full commands: `.github/skills/ci-checks/SKILL.md`.

```bash
npx --yes markdownlint-cli2 "README.md" "docs/**/*.md" "notes/**/*.md" "specs/**/*.md" "evals/**/*.md" "patterns/**/*.md" "experiments/**/*.md"
```

Optional link check:

```bash
docker run --rm -v "${PWD}:/workspace" -w /workspace lycheeverse/lychee:latest \
  --config lychee.toml --cache --max-cache-age 1d '**/*.md'
```

## Key files

| File | Purpose |
|------|---------|
| `.github/copilot-instructions.md` | Canonical AI assistant instructions |
| `.cursor/rules/00_swamy_personal_learning_only.mdc` | Swamy-only personal-learning guard (always-apply) |
| `.cursor/rules/*.mdc` | Cursor rules (10 files) |
| `.cursor/skills.md` | Short habits and CI expectations |
| `.github/skills/` | Bundled agent skills (canonical); mirrored at `.cursor/skills/` |
| `docs/agent-skills.md` | SKILL.md pattern, progressive disclosure, skills mirror |
| `docs/01_repository-structure.md` | Topic folders, naming, on-demand creation (structural SSOT) |
| `.cursor/rules/09_week-companion-architecture.mdc` | Topic unit architecture, on-demand creation, naming contract |
| `.github/prompts/task-prompt.md` | Structured audit template |
| `.github/prompts/smart-prompt-framework-guide.md` | S.M.A.R.T. prompt framework |
| `.github/workflows/ci-skills-parity.yml` | Verifies `.github/skills` ↔ `.cursor/skills` mirror on changes |
| `.github/workflows/ci-agent-docs-guard.yml` | Validates CLAUDE.md, .cursor rules, and key file references |
| `.markdownlint-cli2.yaml` | Markdownlint-CLI2 rules (line length, headings, front matter for skills) |

## SDD topic reference

| Topic area | Focus |
|------------|-------|
| Spec-first design | Writing behavior specs before building |
| Eval-driven development | Designing evaluation loops for AI systems |
| Prompt engineering | Prompt contracts, prompt versioning |
| Deterministic AI | Achieving reliable, predictable LLM behavior |
| LLM pipelines | Composing reliable multi-step AI workflows |

Full contract: `.cursor/rules/09_week-companion-architecture.mdc`.
