---
name: data-preprocessing
description: >-
 Work on the t1-data-preprocessing educational repo (reading notes, examples, quizzes,
 notebooks, model papers, discussion prompts, assignments, src). Use for KDD, data quality, cleaning, transformation,
 reduction, proximity, explainability, pandas/sklearn, zero-copy content, and seven-layer week-aligned structure (this repo only).
license: MIT
---

# Data Preprocessing (M.Sc. DSAI) — project skill

## When to use

- Editing or reviewing `weeks/week1/` through `weeks/week8/`, `weeks/assignments/`, `weeks/model-papers/`, `src/`, or `docs/` in **this** repository.

## Stack (do not confuse with other repos)

- **Python:** pandas, NumPy, scikit-learn; Jupyter notebooks at `weeks/weekN/04_notebook.ipynb`.
- **Tooling:** `uv` at repo root (`pyproject.toml`, `uv.lock`). Commands in Copilot instructions use **PowerShell** on Windows.

## Policies

- **Zero-copy** and **`source-material/`**: `.github/copilot-instructions.md` and `.cursor/rules/01_educational-content-rules.mdc`.
- **Seven-layer week companions (DPP only):** step-numbered files within `weeks/weekN/` folders (`01_reading-notes.md` through `07_assignment.md`). **All eight weeks (1–8) are migrated.** Flat-directory layout is historical reference only. Weeks are added **on demand** — no pre-scaffolding.

## Single sources of truth

- Repository layout and naming: `docs/01_repository-structure.md` and `.cursor/rules/07_file-naming-conventions.mdc`.
- Seven-layer governance: `.cursor/rules/09_week-companion-architecture.mdc`.
- Cursor rules: `.cursor/rules/*.mdc`.
- Short habits index: `.cursor/skills.md`.

## Commands (Windows PowerShell, repo root)

**Environment:**

```powershell
$Env:UV_LINK_MODE = "copy"
uv sync
```

**Jupyter:**

```powershell
jupyter notebook
```

**Python lint** (aligns with `ci-python.yml`):

```powershell
uv run isort --check-only --diff src/
uv run black --check --line-length 127 --target-version py312 src/
uv run flake8 src/ --count --select=E9,F63,F7,F82 --show-source --statistics
uv run flake8 src/ --count --exit-zero --max-complexity=10 --max-line-length=127 --statistics
```

**Markdown** (aligns with `ci-documentation.yml` globs):

```powershell
npx --yes markdownlint-cli2 "README.md" "docs/**/*.md" "src/**/*.md" "tools/**/*.md" "weeks/**/*.md"
```

For the full local CI checklist (including notebook JSON parse and optional Lychee), use the **ci-checks** skill. For week rename / parity audits, use **week-companions**.
