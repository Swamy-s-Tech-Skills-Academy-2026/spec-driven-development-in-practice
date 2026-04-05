---
name: workspace-review
description: Comprehensive workspace review for Data Preprocessing — structure, zero-copy, CI, seven-layer companion parity (weeks on demand), internal path hygiene.
---

# Workspace Review — Data Preprocessing

## Protocol

1. Read `.github/copilot-instructions.md` (**seven-layer** week model for **this repo**, zero-copy, `source-material` rules).
2. Read `.cursor/rules/09_week-companion-architecture.mdc` (week reference, on-demand creation, definition of done, migration SOP).
3. Compare the tree to `docs/01_repository-structure.md` and `README.md`.
4. Python environment: `uv sync` at repo root; use `uv run …` per `pyproject.toml` / CI.
5. **Zero-copy:** public folders contain original synthesis; no inappropriate copies of institution materials.
6. **Seven-layer parity:** for each **finished** week, spot-check all seven layers in `weeks/weekN/` (`01_reading-notes.md` through `07_assignment.md`). All eight weeks (1–8) are migrated.
7. Run the **ci-checks** skill (Python + notebook JSON + markdownlint).
8. Optionally run **docs-verification** and **week-companions** tracker pass.
9. **Agent skills parity:** every `.github/skills/**/SKILL.md` must match `.cursor/skills/**/SKILL.md` byte-for-byte — see `.github/skills/README.md`.

## Output

Critical / Major / Minor findings; CI summary table; doc and companion accuracy notes. Match tone to the repository’s educational rules.
