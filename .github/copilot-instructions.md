# GitHub Copilot Instructions for Spec-Driven Development in Practice

**Version**: 1.0
**Last Updated**: April 5, 2026
**Repository**: `spec-driven-development-in-practice`
**Context**: AI Engineering — Personal learning exploration

**Environment**: Windows, PowerShell, Markdown
**Note**: This is a Markdown-only repository. No Python environment, no Jupyter, no build tools.

---

## Strict scope (non-negotiable)

This repository is **Swamy PKV's personal learning only**. It is **not** for anyone else as courseware, templates, tutorials, or a reference corpus. **Do not** frame content for a general audience (other students, "learners," recruiters). Public visibility is **not** an invitation to use this repo for third-party purposes. Keep `README.md` aligned with the **Scope** section.

---

## Repository Purpose

**Spec-Driven Development in Practice** is **Swamy's** learning workspace for building a principled understanding of Spec-Driven Development (SDD) and deterministic AI system design — **for his use**, not as a shared product for others.

### What This Repository Provides

- **Notes**: Theory and insights on SDD, prompt contracts, and deterministic AI.
- **Specs**: Example behavior specifications and prompt contracts.
- **Evals**: Evaluation strategies and eval loop designs.
- **Patterns**: Reusable SDD patterns and practices.
- **Experiments**: Small experiments and iteration notes.

### Who this is for

- **Swamy PKV only** — personal study and exploration. Not written for, maintained for, or aimed at any other audience.

---

## Repository Structure

**Quick Reference:**

All content lives in top-level topic folders created **on demand**:

- `notes/` — theory, insights, evolving understanding
- `specs/` — behavior specifications and prompt contracts
- `evals/` — evaluation strategies and eval loops
- `patterns/` — SDD patterns and reusable practices
- `experiments/` — small experiments and iterations
- `docs/` — meta-documentation and guides
- `.github/skills/` — Bundled agent skills (`SKILL.md` per subfolder). **Mirrored** at `.cursor/skills/`.

**No pre-scaffolding** — folders are created when work begins. Do not create empty placeholder folders.

**Topic unit architecture**

Files within each folder use two-digit kebab-case numbered names: `01_spec-first-design.md`, `02_eval-loops.md`, etc. Authoritative governance: `.cursor/rules/09_week-companion-architecture.mdc`.

---

## Development Guidelines

### Zero-Copy Policy

- All notes must be original synthesis of ideas and learnings.
- No direct copying from books, papers, or web sources without citation.
- Content must demonstrate genuine understanding in Swamy's own words.

### Voice and Tone

- **Personal learning journey**: Write notes as Swamy's first-person learning journey.
- **Reflection-oriented**: Use "I'm learning…", "I want to understand…", "My take on…"
- **Avoid course framing**: Don't write like a lecturer or course author.

### Documentation Standards

- **`##`** for main topics, **`###`** for subtopics.
- Use blockquotes (`>`) for key definitions or takeaways.
- Use tables for comparing patterns, options, or steps.
- Use Mermaid blocks for flow diagrams and architectures:
  - Node colours: `#ffd966` (highlight), `#dae8fc` (info), `#d5e8d4` (success), `#fff2cc` (neutral), `#f8cecc` (warning)
  - Always include `stroke:#333,color:#000`.

### Naming Conventions

- **No `00_` prefix**: All numbered files start at `01_`.
- **Kebab-case slugs**: `01_spec-first-design.md`, `02_eval-loop-patterns.md`
- **No `XX_` in folder names**: Only files use the numeric prefix.

---

## CI Checks

Markdown lint (aligns with `ci-documentation.yml`):

```powershell
npx --yes markdownlint-cli2 "README.md" "docs/**/*.md" "notes/**/*.md" "specs/**/*.md" "evals/**/*.md" "patterns/**/*.md" "experiments/**/*.md"
```

## Prompt Engineering

When asking Copilot for help:

- Specify which topic area (`specs/`, `evals/`, `patterns/`, `notes/`, `experiments/`).
- State the SDD concept clearly (e.g., "add a note on prompt versioning patterns").
- Reference related files for consistency.

### Prompt templates

- **Task prompt** (structured audit): `.github/prompts/task-prompt.md`
- **S.M.A.R.T. framework guide** (crafting agent instructions): `.github/prompts/smart-prompt-framework-guide.md`
