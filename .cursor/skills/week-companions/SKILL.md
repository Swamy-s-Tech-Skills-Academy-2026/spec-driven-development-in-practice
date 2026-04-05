---
name: week-companions
description: >-
 Seven-layer week companion architecture for t1-data-preprocessing — parity checks, migration SOP,
 definition of done, and migration tracker (Term 1 weeks 01–08). Use when renaming weeks, adding a layer, or auditing
 week bundles. Weeks are added on demand (no pre-scaffolding). Other repos may use different layers.
---

# Week companions — seven-layer SOP (Data Preprocessing)

**Applies to**: `t1-data-preprocessing` **only**. Do not assume the same layer count or names in other course repositories.

**Canonical governance**: `.cursor/rules/09_week-companion-architecture.mdc` and `.github/copilot-instructions.md`.

## Layers (seven)

### Week-based layout (all weeks)

All weeks use `weeks/weekN/` folders with step-numbered filenames (`01_reading-notes.md` through `07_assignment.md`). All eight weeks (1–8) are migrated.

| # | Path | Filename |
|---|------|----------|
| 1 | `weeks/weekN/` | `01_reading-notes.md` |
| 2 | `weeks/weekN/` | `02_examples.md` |
| 3 | `weeks/weekN/` | `03_quiz.md` |
| 4 | `weeks/weekN/` | `04_notebook.ipynb` |
| 5 | `weeks/weekN/` | `05_model-paper.md` |
| 6 | `weeks/weekN/` | `06_discussion.md` |
| 7 | `weeks/weekN/` | `07_assignment.md` |

## Compact migration SOP (reference — migration is complete)

All eight weeks are fully migrated. This SOP is retained for reference if the repository is extended.

1. Confirm **naming contract** and **topic slugs** before renaming (rule `09`).
2. For each **active** week, ensure **seven** companions exist.
3. Add new weeks **only when started**; do not reserve empty future weeks in the repo.
4. After **each** phase: fix links; run **ci-checks** skill (or CI locally).
5. Mark a week **done** only if naming, parity, concept alignment, and notebook health pass.
6. Update **docs** (`docs/01_repository-structure.md`, README) **after** file structure is stable.

## Definition of done (per week)

1. Exactly **seven** primary artifacts exist (one per layer above).
2. Filenames follow step-numbered names inside `weeks/weekN/`.
3. Concepts are consistent across all seven.
4. Notebook is structurally valid and runnable in order.
5. No broken cross-references for that week.
6. Key diagrams from source slides represented as Mermaid blocks (reading-notes) or `matplotlib` cells (notebook) — no university images embedded. See "Visual enrichment from source slides" in `.github/copilot-instructions.md`.

## Golden rules

- Utilities live in **`src/`** and **`tools/`** only — not as substitutes for learning layers.
- **`source-material/`** stays untouched (archival input).
- **No partial week** without an explicit WIP note in `docs/reviews/`.

## Visual enrichment from source slides

Source lecture slides contain diagrams that **cannot** be embedded (zero-copy policy). Three-pathway pattern:

| Slide diagram type | Target layer | Format |
|--------------------|-------------|--------|
| Flowchart / pipeline / hierarchy / decision tree | `01_reading-notes.md` | Mermaid `flowchart` block |
| Scatter / clustering / bar / line chart | `04_notebook.ipynb` | `matplotlib` code cell |
| Transaction / data table | `02_examples.md` | Original Markdown table (different data) |

Mermaid colours: gold `#ffd966` (highlight), blue `#dae8fc`, green `#d5e8d4`, yellow `#fff2cc`, red `#f8cecc`. Always include `stroke:#333,color:#000`.
matplotlib: use `rng = np.random.default_rng(RANDOM_SEED)`, no `plt.savefig()`, title + labelled axes required.

## Migration tracker (template)

Copy into a `docs/reviews/` note while migrating.

### Weekly status (Term 1: weeks 01–08; append rows if the curriculum grows)

| Week | Topic slug | RN | Ex | Qz | Nb | MP | Disc | Asg | Naming | Parity | Links | Quality | Done |
|------|------------|:--:|:--:|:--:|:--:|:--:|:----:|:---:|:------:|:------:|:-----:|:-------:|:----:|
| 01 | foundations-of-data-preprocessing | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| 02 | data-and-attributes | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| 03 | data-quality-and-issues | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| 04 | data-cleaning-and-integration | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| 05 | data-transformation-and-aggregation | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| 06 | data-reduction | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| 07 | proximity-measures | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| 08 | data-explainability | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |

**Columns:** RN = reading-notes, Ex = examples, Qz = quizzes, Nb = notebooks, MP = model papers, Disc = discussion-prompts, Asg = assignments.

### Exit criteria (repo)

- Every week **in the repo** and in scope for this pass: **Done** checked (ignore unstarted future weeks).
- No naming drift vs rules `09` / `07`.
- No broken internal references.
