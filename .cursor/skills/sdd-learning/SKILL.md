---
name: sdd-learning
description: Work on Spec-Driven Development in Practice — notes, specs, evals, patterns, experiments, docs. Markdown-only personal learning for SDD and deterministic AI.
---

# SDD learning workspace — domain context

## When to use

- Editing or reviewing `notes/`, `specs/`, `evals/`, `patterns/`, `experiments/`, or `docs/` in **this** repository.

## Repository facts

- **Markdown only** — no application runtime, no Python toolchain required for this repo.
- **Topic folders on demand** — add `NN_<slug>.md` only when work on that topic begins (see `.cursor/rules/09_week-companion-architecture.mdc`).
- **Voice**: first-person learning journey; avoid instructor or course framing (see `.github/copilot-instructions.md`).
- **Zero-copy**: original synthesis; cite sources when using specific definitions.

## Topic areas (SDD)

| Area | Typical folders | Slug family |
|------|-----------------|-------------|
| Spec-first design | `specs/`, `notes/` | `spec-first-*` |
| Eval-driven development | `evals/`, `patterns/` | `eval-*` |
| Prompt engineering | `specs/`, `patterns/` | `prompt-*` |
| Deterministic AI | `notes/`, `experiments/` | `deterministic-*` |
| LLM pipelines | `patterns/`, `experiments/` | `llm-pipeline-*` |

## Quality hooks

- **Naming**: two-digit prefix, kebab-case slug, never `00_` — `.cursor/rules/07_file-naming-conventions.mdc`.
- **CI**: Markdown lint per `.github/workflows/ci-documentation.yml` — run commands from the **ci-checks** skill.
- **Structure audits**: use **topic-units** and **docs-verification** when checking governance or links.
