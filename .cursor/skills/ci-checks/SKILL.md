---
name: ci-checks
description: >
  Run CI-aligned Markdown quality checks locally for spec-driven-development-in-practice.
  Use when asked to run CI, lint, or verify documentation quality.
---

# CI checks — local runner (Markdown)

Commands mirror `.github/workflows/ci-documentation.yml` and the Markdown guard job in `.github/workflows/ci-agent-docs-guard.yml`.

Repo-wide Markdown rules live in **`.markdownlint-cli2.yaml`** at the repository root;
`markdownlint-cli2` loads it automatically when run from that directory.

## Policy

- **Quality expectations:** `.cursor/rules/03_quality-assurance.mdc`, `.github/copilot-instructions.md`.

## Prerequisites

- **Node.js:** 20.x (match `ci-documentation.yml`) for `markdownlint-cli2`.

## Checks to run

Report each as PASS or FAIL with output.

### 1. markdownlint-cli2 (topic Markdown)

Same globs as `ci-documentation.yml`:

```powershell
npx --yes markdownlint-cli2 "README.md" "docs/**/*.md" "src/notes/**/*.md" "src/specs/**/*.md" "src/evals/**/*.md" "src/patterns/**/*.md" "src/experiments/**/*.md"
```

### 2. markdownlint-cli2 (agent docs)

Aligns with `ci-agent-docs-guard.yml` when editing skills or entrypoints:

```powershell
npx --yes markdownlint-cli2 "CLAUDE.md" ".cursor/skills.md" ".cursor/skills/**/*.md" ".github/skills/**/*.md"
```

### Optional — Lychee (link checker)

When Docker is available:

```bash
docker run --rm -v "${PWD}:/workspace" -w /workspace lycheeverse/lychee:latest --config lychee.toml --cache --max-cache-age 1d '**/*.md'
```

## On failure

- Report file and line when the tool provides them; do not skip silently.

## Summary format

| # | Check | Status | Notes |
|---|--------|--------|-------|
| 1 | markdownlint (topics) | | |
| 2 | markdownlint (agent docs) | | |
| 3 | Lychee (optional) | | |
