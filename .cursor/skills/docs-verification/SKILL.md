---
name: docs-verification
description: Verify markdown structure, seven-layer week companions (DPP), and naming. Use when checking docs accuracy, broken links between layers, or docs vs notebooks.
---

# Documentation Verification — Data Preprocessing

This repo uses a **seven-layer** week bundle (**this repository only**). There is **no** OpenAPI or web API surface to verify.

## Verification matrix

| Concern | Source of truth | Common errors |
|--------|-----------------|---------------|
| Top-level layout | `docs/01_repository-structure.md`, `README.md` | Treating `src/` as a learning layer |
| **Seven-layer** companions | `weeks/weekN/` with step-numbered filenames (`01_reading-notes.md` through `07_assignment.md`). All 8 weeks migrated. | Wrong step number; missing layer file |
| Notebook filenames | `weeks/weekN/04_notebook.ipynb` | Wrong suffix; slug not shared with reading notes |
| Model papers | `weeks/weekN/05_model-paper.md` | Missing paper for a "done" week |
| Discussion prompts | `weeks/weekN/06_discussion.md` | Missing file for a "done" week |
| Assignments | `weeks/weekN/07_assignment.md` | Missing seventh file for a "done" week |
| Week span | Rule `09` | Weeks **on demand** — verify parity only for weeks that exist in the tree |
| Voice / framing | `.github/copilot-instructions.md` | Instructor tone in reading-notes |
| Internal-only paths | `.cursor/rules/06_source_material_rules.mdc` | Mentioning `source-material/` in public docs |

## Paths to spot-check

| Area | Paths |
|------|--------|
| Structure | `docs/01_repository-structure.md`, `README.md` |
| Content | `weeks/week1/` through `weeks/week8/` (all 8 weeks) |
| Trimester extras | `weeks/assignments/`, `weeks/model-papers/` |
| Governance | `.github/copilot-instructions.md`, `.cursor/rules/09_week-companion-architecture.mdc` |

## Output format

Use a table: **File | Status | Issues**. List broken companion links or naming mismatches with concrete paths; offer fixes only when requested.
