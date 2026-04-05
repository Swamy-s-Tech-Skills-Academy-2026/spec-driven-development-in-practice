# Repository skills (Data Preprocessing)

This file is **local to `t1-data-preprocessing`**. It complements `.cursor/rules/*.mdc` and `.github/copilot-instructions.md` with concise “when and how” guidance for assistants editing this repo.

**Strict scope:** This repo is **Swamy PKV’s personal learning only** — not courseware for others. See `README.md` (**Scope**) and `.cursor/rules/00_swamy_personal_learning_only.mdc`.

**Bundled agent skills (folder format):** `.github/skills/` is canonical; `.cursor/skills/` is a **byte-identical mirror** (see `.github/skills/README.md` for the parity check script). Notable bundles: **`data-preprocessing`** (domain), **`week-companions`** (seven-layer parity + migration tracker), **`ci-checks`**, **`docs-verification`**, **`workspace-review`**, **`e2e-testing`**.

---

## Seven-layer week companions (this repo only)

**Other projects** may use a different layer design. For **this** repository, each finished week targets **seven** aligned artifacts in `weeks/weekN/`:

1. `weeks/weekN/01_reading-notes.md`
2. `weeks/weekN/02_examples.md`
3. `weeks/weekN/03_quiz.md`
4. `weeks/weekN/04_notebook.ipynb`
5. `weeks/weekN/05_model-paper.md`
6. `weeks/weekN/06_discussion.md`
7. `weeks/weekN/07_assignment.md`

All eight weeks live under `weeks/week1/` … `weeks/week8/` (see `docs/01_repository-structure.md`). Trimester-level `weeks/assignments/` and `weeks/model-papers/` sit alongside week folders.

**Weeks:** Add **on demand** only — scaffold the seven companions when you start a week; unstarted weeks need no files.

**Learning flow:** theory → examples → quiz → notebook → model paper → discussion prompt → assignment.

**Authoritative detail:** `.cursor/rules/09_week-companion-architecture.mdc`. **Naming patterns:** `.cursor/rules/07_file-naming-conventions.mdc`.

**Term 1 calendar:** weeks **01–08** — Introduction to Data Science, Data, Data Quality and Issues, Data Cleaning, Data Transformation and Aggregation, Data Reduction, Proximity Measures, Data Explainability (see rule `09` §3 for slugs; all eight weeks are fully migrated).

When editing any layer for a week, **review the other six** for terminology, scope, and links.

---

## When editing educational content

- **Voice**: First-person learning journey in reading notes; avoid lecturer or “course” framing (see copilot instructions).
- **Zero-copy**: Original synthesis only in public folders; never copy institution samples into `examples/` or `quizzes/`.
- **`source-material/`**: Read-only staging; never reference in public docs; ignore it in Markdown lint; PDF/PPTX exports stay colocated under `source-material/` (not `docs/exports/`).

---

## Preprocessing substance (what “good” looks like)

- **Train vs test**: Fit scalers, imputers, and encoders on training data only; transform validation/test with the same fitted objects.
- **Missingness**: Distinguish MCAR/MAR/MNAR when discussing imputation.
- **Leakage**: Flag steps that use target or future information.
- **Scale and distance**: Tie normalization/standardization to distance-based methods where relevant.
- **Reproducibility**: Set random seeds; prefer `pathlib`; avoid hardcoded absolute paths.

---

## Tools you may use (maintenance, not student-facing)

- **Markdown / links**: `tools/psscripts/Run-MarkdownLintAndLychee.ps1` (aligns with CI).
- **Zero-copy spot checks**: `tools/psscripts/Verify-ZeroCopy.ps1` when applicable.
- **Conversions**: `tools/psscripts/Convert-SourceMaterialPdfsToMarkdown.ps1`, `tools/pyscripts/pptx_to_md.py`, `tools/pyscripts/pdf_to_md.py` for internal source-material workflows only.

---

## CI expectations

- **Python**: `src/` — black, isort, flake8 (see `.github/workflows/ci-python.yml`).
- **Docs**: Markdown lint and Lychee on configured globs including `weeks/**/*.md`; `source-material/` is excluded from Markdown lint because it is read-only archival input (see `.github/workflows/ci-documentation.yml`).
- **Parity**: `.github/skills/` ↔ `.cursor/skills/` must be byte-identical (see `ci-skills-parity.yml`).
- **Agent docs**: `.github/workflows/ci-agent-docs-guard.yml` validates required `.cursor/rules` files, `CLAUDE.md` / `.cursor/skills.md` references, and skills mirror parity when those paths change.

When in doubt, treat **`docs/01_repository-structure.md`** as the structural single source of truth and keep `.github/copilot-instructions.md` aligned with it.
