# GitHub Copilot Instructions for Spec-Driven Development in Practice

**Version**: 1.4
**Last Updated**: April 8, 2026
**Repository**: `spec-driven-development-in-practice`
**Context**: AI Engineering — Personal learning exploration

**Environment**: Windows, PowerShell, Markdown
**Note**: This is a Markdown-only repository. No Python environment, no Jupyter, no build tools.

---

## Assistant entry points (keep aligned)

| File | Role |
|------|------|
| `CLAUDE.md` | Claude Code entry — structure, skills, CI commands |
| `.cursor/skills.md` | Short Cursor habits; mirrors this file’s scope and CI expectations |
| `docs/agent-skills.md` | How `SKILL.md` bundles relate to rules and this document |
| `docs/01_repository-structure.md` | Structural single source of truth (topic folders, naming) |

**Canonical copy for Copilot:** this file (`.github/copilot-instructions.md`). When any of the above
changes, update the others in the same pass so assistants stay consistent.

---

## Strict scope (non-negotiable)

This repository is **Swamy PKV's personal learning only**. It is **not** for anyone else as courseware,
templates, tutorials, or a reference corpus. **Do not** frame content for a general audience (other
students, "learners," recruiters). Public visibility is **not** an invitation to use this repo for
third-party purposes. Keep `README.md` aligned with the **Scope** section.

---

## Repository Purpose

**Spec-Driven Development in Practice** is **Swamy's** learning workspace for building a principled
understanding of Spec-Driven Development (SDD) and deterministic AI system design — **for his use**,
not as a shared product for others.

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

**Notes** live under **`src/notes/`**. Other topic folders and **`docs/`** are at the repository root,
created **on demand**:

- `src/notes/` — theory, insights, evolving understanding
- `specs/` — behavior specifications and prompt contracts
- `evals/` — evaluation strategies and eval loops
- `patterns/` — SDD patterns and reusable practices
- `experiments/` — small experiments and iterations
- `docs/` — meta-documentation and guides
- `.github/skills/` — Bundled agent skills (`SKILL.md` per subfolder). **Mirrored** at `.cursor/skills/`.

**No pre-scaffolding** — folders are created when work begins. Do not create empty placeholder folders.

### Topic unit architecture

Files within each folder use two-digit kebab-case numbered names: `01_spec-first-design.md`,
`02_eval-loops.md`, etc. (**Never** `00_`.) Authoritative governance:
`.cursor/rules/09_week-companion-architecture.mdc`. **Naming patterns:**
`.cursor/rules/07_file-naming-conventions.mdc`. **Layout write-up:** `docs/01_repository-structure.md`.

---

## Development Guidelines

### Zero-Copy Policy

- All notes must be original synthesis of ideas and learnings.
- No direct copying from books, papers, or web sources without citation.
- Content must demonstrate genuine understanding in Swamy's own words.

### Staging folders (not in public learning docs)

- Do **not** mention **`source-material/`** or **`reference-material/`** in `README.md`, `src/notes/`, root
  topic folders, or **`docs/**/*.md`**.
- Synthesize into topic Markdown; assistants may name these paths only in agent config (this file,
  `CLAUDE.md`, `.cursor/**`, `.github/skills/**`) to state policy — see
  `.cursor/rules/06_source_material_rules.mdc`.

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

Markdown lint (aligns with `ci-documentation.yml`). Agent-docs paths are linted in
`ci-agent-docs-guard.yml` (`CLAUDE.md`, `.cursor/skills.md`, skill trees). Rules:
**`.markdownlint-cli2.yaml`** at the repository root (loaded automatically by `markdownlint-cli2`).
Skills mirror parity: `ci-skills-parity.yml` / `ci-agent-docs-guard.yml`.

```bash
npx --yes markdownlint-cli2 "README.md" "docs/**/*.md" "src/notes/**/*.md" "specs/**/*.md" "evals/**/*.md" "patterns/**/*.md" "experiments/**/*.md"
```

On Windows PowerShell, the same command works as-is.

## Prompt Engineering

When asking Copilot for help:

- Specify which topic area (`specs/`, `evals/`, `patterns/`, `src/notes/`, `experiments/`).
- State the SDD concept clearly (e.g., "add a note on prompt versioning patterns").
- Reference related files for consistency.

### Prompt templates

- **Task prompt** (structured audit): `.github/prompts/task-prompt.md`
- **S.M.A.R.T. framework guide** (crafting agent instructions): `.github/prompts/smart-prompt-framework-guide.md`
