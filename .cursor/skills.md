# Repository skills (Spec-Driven Development in Practice)

This file is **local to `spec-driven-development-in-practice`**. It complements **`CLAUDE.md`** (Claude
Code entry), `.cursor/rules/*.mdc`, and `.github/copilot-instructions.md` (Copilot / general assistants)
with concise guidance for assistants editing this repo.

**Strict scope:** This repo is **Swamy PKV’s personal learning only** — not courseware for others.
See `README.md` (**Scope**) and `.cursor/rules/00_swamy_personal_learning_only.mdc`.

**Bundled agent skills (folder format):** `.github/skills/` is canonical; `.cursor/skills/` is a
**byte-identical mirror** (see `.github/skills/README.md` for the parity script). Bundles:
**`sdd-learning`** (domain), **`topic-units`** (on-demand topic layout + naming), **`ci-checks`**,
**`docs-verification`**, **`workspace-review`**, **`e2e-testing`**.

---

## Topic folders (on demand)

Content lives in top-level topic directories. Create files only when work on that topic begins:

| Folder | Role |
|--------|------|
| `notes/` | Theory, insights, evolving understanding |
| `specs/` | Behavior specifications, prompt contracts |
| `evals/` | Evaluation strategies, eval loop designs |
| `patterns/` | SDD patterns and reusable practices |
| `experiments/` | Small experiments and iteration notes |
| `docs/` | Meta-documentation |

Files use **`NN_<slug>.md`** (two-digit prefix, kebab-case). Never `00_`.

**SSOT write-up:** `docs/01_repository-structure.md`. **Authority:**
`.cursor/rules/09_week-companion-architecture.mdc`. **Naming:**
`.cursor/rules/07_file-naming-conventions.mdc`.

When I edit one file in a topic line of thought, I check sibling notes in the same folder for
consistent terminology and links.

---

## When editing learning content

- **Voice**: first-person learning journey in notes; avoid lecturer or “course” framing (see copilot
  instructions).
- **Zero-copy**: original synthesis in public folders; cite definitions when needed.
- **`source-material/`** (gitignored) and **`reference-material/`** (if present): read-only staging; do **not**
  mention either path in `README.md`, topic folders, or `docs/**/*.md`. Policy:
  `.cursor/rules/06_source_material_rules.mdc`.

---

## SDD substance (what “good” looks like)

- **Specs before build:** behavior described clearly enough that success is checkable.
- **Eval awareness:** note how I would know a spec or prompt is working (metrics, golden cases, human review).
- **Determinism:** call out temperature, tool choice, and other sources of variance when relevant.
- **Prompt contracts:** separate system rules, user input, and expected output shape when documenting prompts.

---

## CI expectations

- **Docs:** Markdown lint on globs in `.github/workflows/ci-documentation.yml`; optional Lychee per
  `lychee.toml` / `CLAUDE.md`.
- **Parity:** `.github/skills/` ↔ `.cursor/skills/` must stay byte-identical
  (`.github/workflows/ci-skills-parity.yml`; enforced when agent docs change via
  `ci-agent-docs-guard.yml`).
- **Agent docs:** `ci-agent-docs-guard.yml` validates required `.cursor/rules` files,
  `CLAUDE.md` / `.cursor/skills.md` references, and skills mirror parity when those paths change.

When in doubt, treat **`README.md`** and **`CLAUDE.md`** as the public structural anchors and keep
`.github/copilot-instructions.md` aligned with them.
