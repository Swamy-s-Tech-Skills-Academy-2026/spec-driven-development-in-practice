# CLAUDE.md — Claude Code entry point

This file provides Claude Code with the essential context for working in this repository. For full details, see the referenced files below.

## Repository

**Data Preprocessing** — academic learning workspace for the M.Sc. DSAI program (Term 1). Python, Jupyter, pandas, scikit-learn. **Not** a web application or production system.

## Non-negotiable: Swamy only

This repository is **Swamy PKV’s personal learning** material. It is **not** maintained for other learners, employers, or the public. Do **not** reword `README.md`, reading notes, or docs to imply a general audience (for example “students,” “learners,” “you” as a tutorial reader) unless Swamy explicitly asks. Preserve the **Scope (read this first)** block in `README.md`.

## Seven-layer week companion architecture (this repo only)

Each **week in the repo** has **seven** aligned learning artifacts in `weeks/weekN/` with step-numbered filenames:

| Step | Filename |
|------|----------|
| 01 | `01_reading-notes.md` |
| 02 | `02_examples.md` |
| 03 | `03_quiz.md` |
| 04 | `04_notebook.ipynb` |
| 05 | `05_model-paper.md` |
| 06 | `06_discussion.md` |
| 07 | `07_assignment.md` |

All 8 weeks are in `weeks/week1/` through `weeks/week8/`. Weeks are created **on demand** — no pre-scaffolding. Other repos may use different layers.

**Governance**: `.cursor/rules/09_week-companion-architecture.mdc`
**Naming**: `.cursor/rules/07_file-naming-conventions.mdc`

## Agent skills (`SKILL.md`)

Bundled on-demand procedures live under `.github/skills/` (mirrored at `.cursor/skills/`). They use YAML frontmatter plus a Markdown body so agents can match tasks without loading everything up front. How that complements `CLAUDE.md`, rules, and MCP: **`docs/agent-skills.md`**.

## Key rules

- **Zero-copy**: All public content must be original synthesis. No copy-paste from textbooks or institution samples.
- **Source material**: `source-material/` is internal and read-only. Never modify, delete, or reference it in public docs. Exclude it from Markdown lint because it is archival input, not maintained authored content.
- **Voice**: First-person learning journey (Swamy's notes). Avoid instructor or "course" framing in reading-notes.
- **Code style**: PEP 8, `pathlib` (no hardcoded paths), comments explain *why* not just *how*.
- **Notebooks**: Context → Data setup → Cleaning/transformation → Validation → Reflection. Seeds set (`rng = np.random.default_rng(RANDOM_SEED)`). Plots labeled. No `plt.savefig()` / no hardcoded paths.
- **Visual enrichment from slides**: PDF/PPTX diagrams in `source-material/` cannot be embedded (zero-copy). Three-pathway: flowcharts/hierarchies → Mermaid block in `01_reading-notes.md`; scatter/bar/clustering charts → `matplotlib` cell in `04_notebook.ipynb`; data/transaction tables → original Markdown table in `02_examples.md`. Mermaid colours: `#ffd966` gold, `#dae8fc` blue, `#d5e8d4` green, `#fff2cc` yellow, `#f8cecc` red — always with `stroke:#333,color:#000`. Full pattern: `.github/copilot-instructions.md` § "Visual enrichment from source slides".

## Environment

```powershell
$Env:UV_LINK_MODE = "copy"
uv sync
jupyter notebook
```

## CI checks (run locally)

Aligned with `.github/workflows/ci-python.yml` and `.github/workflows/ci-documentation.yml`. Full commands: `.github/skills/ci-checks/SKILL.md`.

```bash
uv sync
uv run isort --check-only --diff src/
uv run black --check --line-length 127 --target-version py312 src/
uv run flake8 src/ --count --select=E9,F63,F7,F82 --show-source --statistics
uv run flake8 src/ --count --exit-zero --max-complexity=10 --max-line-length=127 --statistics
uv run python -c "import json,glob; [json.load(open(p,encoding='utf-8')) for p in sorted(glob.glob('weeks/**/*.ipynb', recursive=True))]"
npx --yes markdownlint-cli2 "README.md" "docs/**/*.md" "src/**/*.md" "tools/**/*.md" "weeks/**/*.md"
```

Optional link check (Docker, from repo root): `docker run --rm -v "${PWD}:/workspace" -w /workspace lycheeverse/lychee:latest --config lychee.toml --cache --max-cache-age 1d '**/*.md'` — or `.\tools\psscripts\Run-MarkdownLintAndLychee.ps1`. Fallback: local `lychee` with the same flags.

## Key files

| File | Purpose |
|------|---------|
| `.github/copilot-instructions.md` | Canonical AI assistant instructions (v1.8) |
| `.cursor/rules/00_swamy_personal_learning_only.mdc` | Swamy-only personal-learning guard (always-apply) |
| `.cursor/rules/*.mdc` | Cursor rules (10 files) |
| `.cursor/skills.md` | Short habits and CI expectations |
| `.github/skills/` | Bundled agent skills (canonical); mirrored at `.cursor/skills/` |
| `docs/agent-skills.md` | SKILL.md pattern, progressive disclosure, skills mirror |
| `docs/01_repository-structure.md` | Structural single source of truth |
| `.cursor/rules/09_week-companion-architecture.mdc` | Week bundles: seven layers, naming, migration SOP, assignments transitional note |
| `.github/prompts/task-prompt.md` | Structured audit template |
| `.github/prompts/smart-prompt-framework-guide.md` | S.M.A.R.T. prompt framework |
| `.github/workflows/ci-skills-parity.yml` | Verifies `.github/skills` ↔ `.cursor/skills` mirror on changes |
| `.github/workflows/ci-agent-docs-guard.yml` | Validates CLAUDE.md, .cursor rules, and key file references |

## Week calendar (Term 1) — slug reference

| Week | Focus (course) | Slug |
|------|----------------|------|
| 01 | Introduction to Data Science | `foundations-of-data-preprocessing` |
| 02 | Data | `data-and-attributes` |
| 03 | Data Quality and Issues | `data-quality-and-issues` |
| 04 | Data Cleaning | `data-cleaning-and-integration` |
| 05 | Data Transformation and Aggregation | `data-transformation-and-aggregation` |
| 06 | Data Reduction | `data-reduction` |
| 07 | Proximity Measures | `proximity-measures` |
| 08 | Data Explainability | `data-explainability` |

Full contract: `.cursor/rules/09_week-companion-architecture.mdc` (section 3).
