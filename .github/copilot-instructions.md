# GitHub Copilot Instructions for Data Preprocessing

**Version**: 1.8
**Last Updated**: March 30, 2026
**Repository**: `t1-data-preprocessing`
**Context**: M.Sc. Data Science & AI - Term 1

**Environment**: Windows, PowerShell, Python 3.x, Jupyter Notebooks
**Note**: All commands and scripts should use PowerShell syntax. File paths use Windows format.

---

## Strict scope (non-negotiable)

This repository is **Swamy PKV’s personal learning only**. It is **not** for anyone else as courseware, templates, tutorials, or a reference corpus. **Do not** frame content for a general audience (other students, “learners,” recruiters). Public visibility is **not** an invitation to use this repo for third-party purposes. Keep `README.md` aligned with the **Scope (read this first)** section.

---

## 🎯 Repository Purpose

**Data Preprocessing** is **Swamy’s** academic workspace for building a strong, principled understanding of data preparation. It contains structured notes, examples, quizzes, and hands-on practice material tied to the M.Sc. DSAI program — **for his use**, not as a shared product for others.

### What This Repository Provides

- **Structured Learning Material**: Notes on data quality, cleaning, transformation, and proximity measures.
- **Python Implementations**: Preprocessing concepts using pandas, NumPy, and scikit-learn.
- **Practice & Quizzes**: Worked examples, exercises, and self-assessment quizzes (original synthesis only).
- **Model Papers**: Exam-style papers aligned to each week’s concepts (same slug family as other layers).
- **Discussion Prompts**: Week-scoped reflection / forum prompts (`weeks/weekN/06_discussion.md`).
- **Assignments**: Week-scoped structured deliverables (`weeks/weekN/07_assignment.md`).
- **Resources**: Reference materials for Swamy’s Data Preprocessing study.

### Who this is for

- **Swamy PKV only** — personal study and practice. Not written for, maintained for, or aimed at any other audience.

---

## 📁 Repository Structure

**Quick Reference (public-facing; do not add internal-only paths here):**

All learning content lives under `weeks/`:

- `weeks/week1/` through `weeks/week8/` — seven step-numbered companion files per week (`01_reading-notes.md` → `07_assignment.md`)
- `weeks/assignments/` — trimester-level graded assignment (FIFA21 + Laptop datasets; sub-folders `01-requirements/` through `05-reports/`)
- `weeks/model-papers/` — 5 comprehensive exam papers covering all 8 weeks + `01_model-paper-answers.md`
- `src/` - Python scripts and reusable preprocessing utilities.
- `docs/` - Documentation and repository structure guides (`01_repository-structure.md`, `02_learning-roadmap.md`, `agent-skills.md` for the `SKILL.md` / skills-mirror pattern).
- `tools/` - Repo health, lint, and conversion helpers (PowerShell and Python).
- `.github/skills/` - Bundled agent skills (`SKILL.md` per subfolder: e.g. `data-preprocessing`, `week-companions`, `ci-checks`). **Mirrored** at `.cursor/skills/` (same bytes — see `.github/skills/README.md`).
- `README.md` - Project overview and topics covered.

**Seven-layer week companion architecture (this repo only)**

Learning content is organized in **week bundles** created **on demand**: add a new week only when you start that week — **do not** pre-create empty companions for future weeks. For any week that **exists** in the repo, use the same two-digit prefix `XX_` and the **same topic slug** `<slug>` (kebab-case) across **all seven** learning layers. Utilities (`src/`, `tools/`) are **not** learning layers. **Other repositories** may use a different layer set — do not assume the same model elsewhere.

Authoritative governance: `.cursor/rules/09_week-companion-architecture.mdc`.

**Layers (learner order, in `weeks/weekN/`):**

1. **Theory** — `01_reading-notes.md`
2. **Practice** — `02_examples.md`
3. **Quizzes** — `03_quiz.md`
4. **Experiments** — `04_notebook.ipynb`
5. **Model papers** — `05_model-paper.md` (answers in-file or paired answers file)
6. **Discussion prompt** — `06_discussion.md`
7. **Assignment** — `07_assignment.md`

**Week ↔ topic slug (reference for weeks already in the tree; extend on demand):**

| Week | Focus (course) | Slug `<slug>` |
|------|----------------|----------------|
| 01 | Introduction to Data Science | `foundations-of-data-preprocessing` |
| 02 | Data | `data-and-attributes` |
| 03 | Data Quality and Issues | `data-quality-and-issues` |
| 04 | Data Cleaning | `data-cleaning-and-integration` |
| 05 | Data Transformation and Aggregation | `data-transformation-and-aggregation` |
| 06 | Data Reduction | `data-reduction` |
| 07 | Proximity Measures | `proximity-measures` |
| 08 | Data Explainability | `data-explainability` |

All eight weeks (01–08) are fully migrated. If the curriculum extends beyond 08, use the slug above, add all seven companions **on demand**, and update this table plus rule `09` / `CLAUDE.md` / `docs/02_learning-roadmap.md` in the same maintenance pass. `docs/01_repository-structure.md` references rule `09` for the slug map.

**Example — Week 01 (week-based folder layout):**

All weeks use `weeks/weekN/` folders with step-numbered filenames:

```text
weeks/week1/
├── 01_reading-notes.md
├── 02_examples.md
├── 03_quiz.md
├── 04_notebook.ipynb
├── 05_model-paper.md
├── 06_discussion.md
└── 07_assignment.md
```

**Learning flow**: Read theory → Practice examples → Do quiz → Run notebook → Validate with model paper → Engage with discussion prompt → Complete assignment.

**Core rules**

- **Unstarted weeks** need no files. A week is **not complete** until all **seven** primary layer files exist and align conceptually.
- If one layer for a week is updated, **review the other six** for terminology, scope, and links.

**Migration SOP (reference — migration is complete)**

All eight weeks are fully migrated to `weeks/weekN/`. This SOP is retained for reference if the repository is extended.

1. Freeze naming + slugs. 2. Inventory and map renames. 3. Migrate in phases. 4. Fix links after each phase. 5. Update `docs/01_repository-structure.md` / README **after** the tree is stable.

**Quality gates (quick)**

- Naming: step-numbered filenames within `weeks/weekN/` (`01_reading-notes.md` through `07_assignment.md`).
- Parity: seven artifacts per finished week.
- Integrity: zero-copy / citations.
- Links: internal navigation still valid.
- Notebooks: valid structure, executable order, headings match the week slug family.

---

## 🔧 Development Guidelines

### Source Material Staging (Internal only — do not mention in public documentation)

The concept and path of source-material are **internal and confidential** between the author and AI/Copilot. Do not mention, reference, or describe them in any public-facing documentation (README, docs/, examples, repository structure documents, or any content that may be shared or published).

**🚫 Critical Restrictions:**

- **Read-Only Policy**:
 - **NEVER modify** any file inside `source-material/`
 - **NEVER overwrite** any file inside `source-material/`
 - **NEVER edit** content even if it contains errors
 - Files are **permanent reference materials**
 - **IGNORE `source-material/` in Markdown linting** because it is archival input, not maintained authored content.

- **No Deletion Policy**:
 - **NEVER delete** anything from `source-material/`
 - Content remains even after migration
 - Serves as **permanent historical reference**

- **Export Location Policy (PDF/PPTX conversions)**:
 - **NEVER write exported/converted files to `docs/exports/`** when the input comes from `source-material/`.
 - For `.pdf` / `.pptx` conversions, create outputs **in the same `source-material` location tree** as the input file (same folder or a child folder under that same branch).
 - Keep the conversion local to its source-material path so origin and extracted artifact stay together.

**🔄 Migration Workflow:**
1. Read from `source-material/` to understand concepts
2. Synthesize - Rewrite in your own words (NO copy-paste)
3. Publish to educational folders — **`weeks/weekN/`** with step-numbered filenames (`01_reading-notes.md` through `07_assignment.md`), plus `docs/` or `src/` when appropriate (utilities stay in `src/`, not mixed into layer folders)
4. Cite when using specific definitions/theorems

**✅ Zero-Copy Policy:**
- **Good Synthesis**: Demonstrates understanding, uses different vocabulary, explains concepts
- **Bad Synthesis (Rejected)**: Word-for-word copying, minor rephrasing, close paraphrasing without understanding

**📁 Purpose**: The folder is a staging area for raw author content, book transcripts/excerpts, PDF extracts, reference materials, and original code examples. These materials remain untouched and serve as permanent references while you create original, synthesized educational content.

### Zero-Copy Policy
- All notes and code must be original syntheses of learning materials.
- No direct copying from textbooks without citation.
- **Examples must be original**: Even when the source uses common examples (e.g., common datasets or textbook cases), create fresh scenarios in your own words.
- **Do not copy author/course samples into public folders**: Graded quizzes, practice quizzes, or other institutional samples stay as reference only (e.g. in internal staging). Content in `weeks/weekN/02_examples.md` must be original, not verbatim or near-verbatim copies of those samples.

### Project Focus
- **Preprocessing Accuracy**: Ensure cleaning, scaling, and transformation steps are correct and reproducible.
- **Code Quality**: Use clear, well-commented Python code (pandas, scikit-learn).
- **Explainability**: Document why each preprocessing step is applied and how it affects downstream results.

### Code Style (Python)
- Follow PEP 8 style guide.
- Use meaningful variable names (e.g., `cleaned_df` instead of `df2`).
- Use type hints where appropriate.
- **Comments**: Comment liberally to explain the *why* of the operation, not just the *how*.
- **No hardcoded paths**: Use `pathlib` or relative paths.

### Code Comments Philosophy
- Explain the **conceptual reason** for the step (e.g., "Standardize so distance-based algorithms are not dominated by scale").
- Explain the **effect** (e.g., "Min-max scaling maps values to [0, 1] for this feature").
- Not just syntax explanation (avoid: "This creates a DataFrame").

### Documentation Standards
- **Review reports**: All review reports go in `docs/reviews/`.
- **Reference materials**: General reference docs go in `docs/reference/`.
- **Reading notes**: Synthesized study notes go in `weeks/weekN/01_reading-notes.md`.

### Voice and Tone
- **Personal learning journey**: Write reading notes as Swamy's first-person learning journey (avoid "course" or instructor tone).
- **Reflection-oriented**: Prefer "I'm learning…", "I plan to…", "I want to be able to…" over generic descriptions.
- **Avoid course framing**: Don't title notes as "Course …" or write like a lecturer; write like my own notes (e.g., "My learning journey", "My revision notes").

### Naming Conventions

**Topic Numbering:**
- **No `00_` prefix**: Files and folders must NOT use the `00_` prefix. Use `01_`, `02_`, etc. for numbered sequences.
- **Sequential numbering**: Start from `01_` and increment logically.

**File naming pattern** (step-numbered within `weeks/weekN/`):

- Reading notes: `weeks/weekN/01_reading-notes.md`
- Examples: `weeks/weekN/02_examples.md`
- Quiz: `weeks/weekN/03_quiz.md`
- Notebook: `weeks/weekN/04_notebook.ipynb`
- Model paper: `weeks/weekN/05_model-paper.md`
- Discussion: `weeks/weekN/06_discussion.md`
- Assignment: `weeks/weekN/07_assignment.md`

Where `N` is the week number (1–8). The step prefix (01–07) identifies the layer; the folder name (`weekN`) identifies the week.

### Notebook Guidelines
- Structure notebooks with clear headers. Preferred **conceptual flow**: Context → Data setup → Cleaning/transformation → Validation → Reflection (aligned with the seven-layer week policy for this repo).
- Include markdown cells explaining the preprocessing concept before the code.
- Notebook titles and major headings should match the **same week** as reading notes for that week.
- Use LaTeX for formulas (e.g., normalization, distance measures).
- Ensure all cells run sequentially; avoid hidden state.

### Visual enrichment from source slides

Source lecture slides (`source-material/livesessions/wN/`) contain conceptual diagrams that **cannot** be embedded directly (zero-copy policy). Capture the same knowledge as original synthesis using this three-pathway decision:

| Diagram type in source slide | Target layer | Output format |
|------------------------------|-------------|---------------|
| Flowchart, pipeline, hierarchy, decision tree | `01_reading-notes.md` | Mermaid ` ```mermaid ``` ` block |
| Scatter plot, clustering visual, bar / line chart | `04_notebook.ipynb` | `matplotlib` code cell |
| Transaction table, data table, entity list | `02_examples.md` | Original Markdown table (different data from source) |

Never embed or reproduce a university-originated image verbatim.

**Mermaid style convention** (consistent across all weeks):

| Node role | Fill attribute |
|-----------|----------------|
| Highlight / active step | `fill:#ffd966` (gold) |
| Info / secondary node | `fill:#dae8fc` (blue) |
| Success / positive path | `fill:#d5e8d4` (green) |
| Neutral / alternative | `fill:#fff2cc` (yellow) |
| Warning / error path | `fill:#f8cecc` (red) |

Always include `stroke:#333,color:#000` with every `fill`.

**matplotlib cell rules:**

- Random state: `rng = np.random.default_rng(RANDOM_SEED)` — never `np.random.seed()` bare call.
- No `plt.savefig()` and no hardcoded paths — display only (`plt.show()`).
- Every plot needs a title and labelled axes.

**After each enrichment pass:** validate with `npx markdownlint-cli2 "weeks/**/*.md"` and the notebook JSON CI check (see `ci-checks` skill).

### Preferred authoring rhythm (per week)

1. **Theory** (`weeks/weekN/01_reading-notes.md`) — draft concepts first.
2. **Practice** (`weeks/weekN/02_examples.md`) — derive worked examples from the notes.
3. **Quiz** (`weeks/weekN/03_quiz.md`) — test the same learning objectives.
4. **Experiments** (`weeks/weekN/04_notebook.ipynb`) — implement and visualize.
5. **Model paper** (`weeks/weekN/05_model-paper.md`) — exam-style validation and answers.
6. **Discussion** (`weeks/weekN/06_discussion.md`) — reflection / cohort discussion aligned to the week.
7. **Assignment** (`weeks/weekN/07_assignment.md`) — structured deliverable, rubric, and submission expectations.

Before marking a week done: **parity check** across all seven files (naming + links + concept alignment).

---

## 🚀 Running the Code

**Python Environment:**
```powershell
# Optional: Suppress cross-drive hardlink warnings (if expected)
$Env:UV_LINK_MODE = "copy"

# Create virtual environment and install dependencies
uv sync
```

**Jupyter:**
```powershell
jupyter notebook
```

## 🧠 Prompt Engineering

When asking Copilot for help:
- Specify the **week** or `XX_` prefix and layer(s) you are editing so companion files stay aligned (**seven-layer** rule for this repo).
- Specify the preprocessing task clearly (e.g., "Handle missing data with KNN imputation").
- Request Python implementation using specific libraries (e.g., "Use `sklearn.preprocessing.StandardScaler`").
- Ask for explanations of how preprocessing affects distance measures or model behavior.

### Prompt templates

- **Task prompt** (structured audit): `.github/prompts/task-prompt.md`
- **S.M.A.R.T. framework guide** (crafting agent instructions): `.github/prompts/smart-prompt-framework-guide.md`
