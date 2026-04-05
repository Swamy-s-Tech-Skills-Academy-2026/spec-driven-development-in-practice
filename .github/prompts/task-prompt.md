# Data Preprocessing Repository Verification and Content Enhancement

## Context

You are working with **t1-data-preprocessing**, an academic learning workspace for **Data Preprocessing** in the M.Sc. Data Science & AI program . The repository contains structured notes, examples, quizzes, notebooks, model papers, discussion prompts, assignments, and utilities.

**Repository structure:**

- `weeks/week1/` through `weeks/week8/` — seven step-numbered companion files per week (`01_reading-notes.md` → `07_assignment.md`)
- `weeks/assignments/` — trimester-level graded assignment (FIFA21 + Laptop datasets)
- `weeks/model-papers/` — 5 comprehensive exam papers covering all 8 weeks + consolidated answers guide
- `src/` - Reusable preprocessing utilities (Python) — **not** a learning layer
- `docs/` - Documentation and structure guides
- `.github/` - Workflows and templates
- `.cursor/` - Cursor AI project rules

**Term 1 calendar:** Weeks **01–08** with course topics and canonical slugs are defined in `.cursor/rules/09_week-companion-architecture.mdc` §3 and `.github/copilot-instructions.md`.

**Primary objective:**
Perform a structured audit using this repo's standards. Verify file contents, **seven-layer week companion** naming and parity for **weeks that exist** in the tree (weeks are added on demand — do not expect placeholder future weeks), zero-copy policy, and produce actionable suggestions.

---

## Verification checks

### A. File content and structure

- Verify markdown and notebook formatting compliance.
- Check completeness and consistency with course coverage.
- Verify zero-copy policy compliance (no copy-paste artifacts from textbooks).

### B. Seven-layer week companion architecture (this repository)

- For each week, expect seven artifacts in `weeks/weekN/`: `01_reading-notes.md`, `02_examples.md`, `03_quiz.md`, `04_notebook.ipynb`, `05_model-paper.md`, `06_discussion.md`, `07_assignment.md`.
- **On demand:** only weeks present in the repo need seven companions; do not require files for unstarted weeks.
- **Do not** assume other course repos use the same layer design.
- Authoritative reference: `.cursor/rules/09_week-companion-architecture.mdc` and `.github/copilot-instructions.md`.

### C. Naming conventions

- All weeks use step-numbered filenames within `weeks/weekN/` folders.
- Python in `src/`: snake_case (e.g. `data_cleaning.py`).

### D. Content quality

- Preprocessing concepts explained before code.
- Code comments explain the *why* of preprocessing steps.
- Formulas in LaTeX where applicable.
- Reproducibility (seeds, paths via pathlib).

### E. Cross-references and links

- Internal links (e.g. README to docs) valid.
- No broken references in docs or README.
- Companion links across the **seven** layers for each week resolve.

---

## Deliverables

1. Summary of compliance with repository structure and naming.
2. List of issues (file path, severity, description, suggested fix).
3. Up to three clear next steps to improve the repository.

---

## Behavioral expectations

- **Learning-workspace focus**: Prioritize clarity, correctness, and explainability.
- **Zero-copy**: Flag content that appears to be direct copy from source material.
- **Preprocessing accuracy**: Ensure cleaning, scaling, and transformation steps are correct and documented.
- **Reproducibility**: Check that notebooks and code can be run with `uv sync` and standard setup.
