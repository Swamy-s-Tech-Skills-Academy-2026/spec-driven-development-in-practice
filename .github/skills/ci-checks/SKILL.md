---
name: ci-checks
description: Run CI-aligned quality checks locally for Data Preprocessing (Python lint on src/, notebook JSON parse, markdown lint). Use when asked to run CI, lint, test, or verify code quality.
---

# CI Checks — Local Runner (Data Preprocessing)

Commands mirror `.github/workflows/ci-python.yml` and `.github/workflows/ci-documentation.yml`.

## Policy

- **Quality expectations:** `.cursor/rules/03_quality-assurance.mdc`, `.cursor/rules/09_week-companion-architecture.mdc` (when editing week bundles), and `.github/copilot-instructions.md`.

## Prerequisites

- **Python:** `uv` at repo root — run `uv sync` (on Windows, optionally `$Env:UV_LINK_MODE = "copy"` first).
- **Node.js:** **20.x** (match `ci-documentation.yml`) for `markdownlint-cli2`.

## Checks to run

Report each as PASS or FAIL with output.

### 1. isort (check only)

```powershell
uv run isort --check-only --diff src/
```

### 2. Black (check only)

```powershell
uv run black --check --line-length 127 --target-version py312 src/
```

### 3. flake8

```powershell
uv run flake8 src/ --count --select=E9,F63,F7,F82 --show-source --statistics
uv run flake8 src/ --count --exit-zero --max-complexity=10 --max-line-length=127 --statistics
```

### 4. Notebook JSON parse (basic)

Same logic as `ci-python.yml` — all notebooks under `weeks/**/*.ipynb`:

```powershell
uv run python -c "import json,glob; [json.load(open(p,encoding='utf-8')) for p in sorted(glob.glob('weeks/**/*.ipynb', recursive=True))]"
```

If `uv run` fails on your machine with “Failed to canonicalize script path”, use the project venv or `py -3.12 -m` with the same modules (`isort`, `black`, `flake8`).

### 5. markdownlint-cli2

Same globs as `ci-documentation.yml`:

```powershell
npx --yes markdownlint-cli2 "README.md" "docs/**/*.md" "src/**/*.md" "tools/**/*.md" "weeks/**/*.md"
```

### Optional — Lychee (link checker)

When your environment supports it (see repo scripts):

```powershell
.\tools\psscripts\Run-MarkdownLintAndLychee.ps1 -LycheeOnly
```

## Execution strategy

Run 1–4 from repo root with `uv`; run 5 from repo root with Node available. Parallelize Python checks where helpful.

## On failure

- **Black / isort:** suggest `uv run black src/` / `uv run isort src/` from repo root (verify project conventions first).
- **flake8 / markdownlint / JSON parse:** report file (and line if applicable); do not skip silently.

## Summary format

| # | Check | Status | Notes |
|---|--------|--------|-------|
| 1 | isort | | |
| 2 | black | | |
| 3 | flake8 | | |
| 4 | notebooks JSON | | |
| 5 | markdownlint | | |
