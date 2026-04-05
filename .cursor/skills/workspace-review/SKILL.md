---
name: workspace-review
description: >
  Comprehensive workspace review for spec-driven-development-in-practice — structure, zero-copy,
  Markdown CI, topic-unit governance, internal path hygiene.
---

# Workspace review — Spec-Driven Development in Practice

## Protocol

1. Read `.github/copilot-instructions.md` (scope, zero-copy, voice, topic folders).
2. Read `.cursor/rules/09_week-companion-architecture.mdc` (on-demand creation, naming).
3. Compare the tree to `README.md` and `CLAUDE.md`. If `docs/01_repository-structure.md` exists, use it
   as extra structure context.
4. **Zero-copy:** public Markdown is original synthesis; flag close paraphrase of external sources without citation.
5. **Topic units:** spot-check that files use `NN_<slug>.md` and sit in the right folder; no empty stubs.
6. Run the **ci-checks** skill (markdownlint on topic globs; add agent-docs globs if `.cursor/` or
   `.github/skills/` changed).
7. Optionally run **docs-verification** and **topic-units** passes on changed paths.
8. **Agent skills parity:** every `.github/skills/**/SKILL.md` and `README.md` must match
   `.cursor/skills/` byte-for-byte — see `.github/skills/README.md`.

## Output

Critical / Major / Minor findings; CI summary table; doc and naming notes. Match tone to this
repository’s personal-learning rules.
