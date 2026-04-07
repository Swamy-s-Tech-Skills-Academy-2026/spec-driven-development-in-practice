---
name: docs-verification
description: Verify Markdown structure, topic-folder layout, and naming for spec-driven-development-in-practice. Use when checking docs accuracy or broken internal links.
---

# Documentation verification — SDD learning repo

This repository is **Markdown-only**. There is no OpenAPI or web API surface to verify.

## Verification matrix

| Concern | Source of truth | Common errors |
|---------|-----------------|---------------|
| Top-level layout | `README.md`, `CLAUDE.md`, `.github/copilot-instructions.md` | Listing internal-only paths in public docs |
| Topic folders | `.cursor/rules/09_week-companion-architecture.mdc` | Wrong folder for content type (e.g. spec content under `src/notes/` when it belongs in `src/specs/`) |
| File naming | `.cursor/rules/07_file-naming-conventions.mdc` | `00_` prefix; missing or non-kebab slug |
| On-demand rule | Rule `09` | Stub files for topics not yet started |
| Voice / framing | `.github/copilot-instructions.md` | Instructor tone; third-party audience framing |
| Internal-only material | `.cursor/rules/06_source_material_rules.mdc` | Naming `source-material/` or `reference-material/` in `README.md`, `src/**` topics, or `docs/**/*.md` |

## Paths to spot-check

| Area | Paths |
|------|--------|
| Entrypoints | `README.md`, `CLAUDE.md` |
| Topic content | `src/notes/`, `src/specs/`, `src/evals/`, `src/patterns/`, `src/experiments/` (as present) |
| Meta docs | `docs/` (as present) |
| Governance | `.cursor/rules/09_week-companion-architecture.mdc` |

## Output format

Use a table: **File | Status | Issues**. List broken links and naming problems with concrete paths; suggest fixes when useful.
