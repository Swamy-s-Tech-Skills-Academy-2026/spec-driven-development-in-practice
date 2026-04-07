---
name: topic-units
description: Topic unit architecture for spec-driven-development-in-practice — on-demand folders, NN_kebab-case naming, governance. Use when adding topics or auditing layout.
---

# Topic units — architecture and checks

**Applies to**: `spec-driven-development-in-practice` only. Other repositories may use different layouts.

## Topic folders (on demand)

| Folder | Role |
|--------|------|
| `notes/` | Theory, foundations, evolving understanding |
| `specs/` | Behavior specifications, prompt contracts |
| `evals/` | Evaluation strategies, eval loop designs |
| `patterns/` | SDD patterns and reusable practices |
| `experiments/` | Small experiments and iteration notes |
| `docs/` | Meta-documentation and repository guides |

## Naming contract

- Files: `NN_<slug>.md` (two-digit prefix, kebab-case slug). Never `00_`.
- Do not pre-scaffold empty files for topics not yet started.

## Audit checklist

When adding or changing a topic file:

1. Content lives in the correct folder for its role (spec vs note vs eval, etc.).
2. Filename matches `NN_<slug>.md`.
3. No duplicate home for the same concept across folders.
4. Relative internal links resolve.
5. Zero-copy and voice rules hold (`.cursor/rules/01_educational-content-rules.mdc`).
6. No mention of `source-material/` or `reference-material/` in topic Markdown (rule `06`).

**Authority**: `.cursor/rules/09_week-companion-architecture.mdc`.
