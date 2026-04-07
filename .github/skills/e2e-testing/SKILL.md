---
name: e2e-testing
description: >
  Smoke verification for spec-driven-development-in-practice — Markdown lint and optional link check.
  Use when asked to smoke-test the workspace end-to-end.
---

# Smoke verification — Markdown workspace

There is no deployed application or Python package in this repository. “End-to-end” here means
**documentation quality checks** that align with CI.

## Prerequisites

- **Node.js** 20.x for `markdownlint-cli2`
- Optional: Docker for Lychee (see **ci-checks** skill)

## Suggested sequence

1. **Markdown lint (topics)** — same as `ci-documentation.yml`:

   ```powershell
   npx --yes markdownlint-cli2 "README.md" "docs/**/*.md" "src/notes/**/*.md" "specs/**/*.md" "evals/**/*.md" "patterns/**/*.md" "experiments/**/*.md"
   ```

2. **Markdown lint (agent docs)** — if skills, rules, or `CLAUDE.md` changed:

   ```powershell
   npx --yes markdownlint-cli2 "CLAUDE.md" ".cursor/skills.md" ".cursor/skills/**/*.md" ".github/skills/**/*.md"
   ```

3. **Links (optional)** — run Lychee per **ci-checks** skill when a full link audit is requested.

## Summary

Report each step **PASS** / **FAIL** / **SKIPPED**. Note any glob paths with no matching files
(expected until topic folders gain content).
