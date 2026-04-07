# Repository structure

This file is the **single place** for how learning content is laid out in this repository. It matches
`README.md` and `.cursor/rules/09_week-companion-architecture.mdc` (topic units and naming).

## Root layout

- **`docs/`** (this folder) — meta-documentation at the repository root.
- **`src/notes/`** — personal learning notes only.
- **`specs/`**, **`evals/`**, **`patterns/`**, **`experiments/`** — other topic folders at the repository
  root (on demand).

Agent configuration (`.cursor/`, `.github/`, `CLAUDE.md`) stays at the repository root.

## Topic folders (on demand)

Folders are created **only when work on that topic starts**. Do not add empty trees or placeholder files.

| Folder | Purpose |
|--------|---------|
| `src/notes/` | Theory, insights, evolving understanding |
| `specs/` | Behavior specifications and prompt contracts |
| `evals/` | Evaluation strategies and eval loop designs |
| `patterns/` | SDD patterns and reusable practices |
| `experiments/` | Small experiments and iterations |
| `docs/` | Meta-documentation and guides (this folder) |

## File naming

Within each topic folder, files use:

- A **two-digit prefix**: `01_`, `02_`, … (**never** `00_`)
- A **kebab-case** slug: e.g. `01_eval-loop-design.md`
- Extension **`.md`**

Full governance and extension rules:
[`.cursor/rules/09_week-companion-architecture.mdc`](../.cursor/rules/09_week-companion-architecture.mdc).

## What this repository is not

- Not a web application or production codebase
- Not a Python or Node application root (no app `package.json` / `pyproject.toml` here)
- Not a place to duplicate the same note across multiple topic folders

## Related meta docs

- [`agent-skills.md`](./agent-skills.md) — bundled assistant skills and mirror layout
