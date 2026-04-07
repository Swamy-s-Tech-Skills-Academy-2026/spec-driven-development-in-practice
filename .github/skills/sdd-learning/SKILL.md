---
name: sdd-learning
description: Work on Spec-Driven Development in Practice — notes, specs, evals, patterns, experiments, docs. Markdown-only personal learning for SDD and deterministic AI.
---

# SDD learning workspace — domain context

## When to use

- Editing or reviewing `src/notes/`, `src/specs/`, `src/evals/`, `src/patterns/`, `src/experiments/`, or
  `docs/` in **this** repository.

## Repository facts

- **Markdown only** — no application runtime, no Python toolchain required for this repo.
- **Topic folders on demand** — add `NN_<slug>.md` only when work on that topic begins (see
  `.cursor/rules/09_week-companion-architecture.mdc` and `docs/01_repository-structure.md`).
- **Assistant anchors** — `CLAUDE.md`, `.cursor/skills.md`, and `.github/copilot-instructions.md` should
  stay consistent on scope, folder list, and CI commands.
- **Voice**: first-person learning journey; avoid instructor or course framing (see
  `.github/copilot-instructions.md`).
- **Zero-copy**: original synthesis; cite sources when using specific definitions.
- **Staging**: do not mention `source-material/` or `reference-material/` in `README.md`, any `src/**`
  topic Markdown, or `docs/**/*.md` (rule `06`).

## Topic areas (SDD)

| Area | Typical folders | Slug family |
|------|-----------------|-------------|
| Spec-first design | `src/specs/`, `src/notes/` | `spec-first-*` |
| Eval-driven development | `src/evals/`, `src/patterns/` | `eval-*` |
| Prompt engineering | `src/specs/`, `src/patterns/` | `prompt-*` |
| Deterministic AI | `src/notes/`, `src/experiments/` | `deterministic-*` |
| LLM pipelines | `src/patterns/`, `src/experiments/` | `llm-pipeline-*` |

## Quality hooks

- **Naming**: two-digit prefix, kebab-case slug, never `00_` — `.cursor/rules/07_file-naming-conventions.mdc`.
- **CI**: Markdown lint per `.github/workflows/ci-documentation.yml` — run commands from the **ci-checks** skill.
- **Structure audits**: use **topic-units** and **docs-verification** when checking governance or links.
