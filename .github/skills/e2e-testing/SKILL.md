---
name: e2e-testing
description: Smoke verification for the Data Preprocessing repo (environment, dependencies, notebook JSON, optional manual notebook run). Use when asked to smoke-test or validate the workspace end-to-end.
---

# Smoke / E2E-style verification — Data Preprocessing

There is no deployed web application in this repository. “End-to-end” here means **environment + parse + optional notebook execution**.

## Prerequisites

- Python 3.12+ with **`uv`** at repo root
- Optional: Jupyter for manual **Kernel → Restart & Run All**

## Suggested sequence

1. **Dependencies**

 ```powershell
 $Env:UV_LINK_MODE = "copy"
 uv sync
 ```

2. **Import smoke (optional)**

 ```powershell
 uv run python -c "import pandas, numpy, sklearn; print('ok')"
 ```

3. **Notebook JSON** — same as CI / **ci-checks** skill:

 ```powershell
 uv run python -c "import json,glob; [json.load(open(p,encoding='utf-8')) for p in sorted(glob.glob('weeks/**/*.ipynb', recursive=True))]"
 ```

4. **Manual (recommended for releases)** — open representative `weeks/weekN/04_notebook.ipynb`, run all cells top to bottom; confirm plots and outputs match intent.

## Summary

Report each step **PASS** / **FAIL** / **SKIPPED** (e.g. skip manual run if not requested). Note any kernel or data-path issues explicitly.
