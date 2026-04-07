# Repository structure

This file is the **single place** for how learning content is laid out in this repository. It matches
`README.md` and `.cursor/rules/09_week-companion-architecture.mdc` (topic units and naming).

## Root layout

- **`docs/`** (this folder) — meta-documentation at the repository root.
- **`src/`** — all **topic** trees (`notes`, `specs`, `evals`, `patterns`, `experiments`) live here.

Agent configuration (`.cursor/`, `.github/`, `CLAUDE.md`) stays at the repository root.

## Topic folders (on demand)

Folders are created **only when work on that topic starts**. Empty trees may hold a `.gitkeep` until the
first real `NN_<slug>.md` file lands.

| Folder | Purpose |
|--------|---------|
| `src/notes/` | Theory, insights, evolving understanding |
| `src/specs/` | Behavior specifications and prompt contracts |
| `src/evals/` | Evaluation strategies and eval loop designs |
| `src/patterns/` | SDD patterns and reusable practices |
| `src/experiments/` | Small experiments and iterations |
| `docs/` | Meta-documentation and guides (this folder) |

## File naming

Within each topic folder under `src/`, files use:

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
- [`02_project-playbook.md`](./02_project-playbook.md) — repeatable steps from this repo to future projects
