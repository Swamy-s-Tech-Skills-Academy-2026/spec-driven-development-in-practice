# S.M.A.R.T. Prompt Framework for Coding Agents

**Data Preprocessing (M.Sc. DSAI) Edition** — Framework for creating high-quality coding agent instructions aligned with this repository's learning-workspace context.

---

## The S.M.A.R.T. Framework

```text
S - Specific Role Definition (e.g., Senior Python Developer, Data Preprocessing Specialist)
M - Mission-Critical Requirements (What must be accomplished with measurable outcomes)
A - Audience-Aware Communication (Team expertise level, domain context)
R - Response Format Control (Code structure, documentation style)
T - Task-Oriented Constraints (Technology stack, forbidden actions)
```

---

## Data Preprocessing Repository Alignment

When creating prompts for this repo, consider:

- **Prompt Pattern**: Is this instruction-based, role-based, chain-of-thought, or evaluation?
- **Use Case Context**: What task type (reading-notes, examples, quizzes, notebooks, src utilities)?
- **Seven-Layer Week Companion Architecture (DPP only)**: reading-notes → examples → quizzes → notebooks → model-papers → discussion-prompts → assignments. Weeks are added **on demand** (no pre-scaffolding). Same `XX_` + topic slug across all seven for each week in the repo; see `.cursor/rules/09_week-companion-architecture.mdc`. Other repos may differ.
- **Template Reusability**: Can this prompt be templated for reuse across topics (e.g., weeks 01–08)?

---

## Problem Statement Template

Use this template for coding agent tasks:

```markdown
## ROLE DEFINITION

You are a [Specific Role] specializing in [Technology Stack] with expertise in [Domain Areas]

## MISSION

[Clear, specific objective with measurable outcomes]

## CONTEXT

[Brief overview of current situation and progress made]

## CURRENT STATUS

- **Progress Made**: [Specific achievements and metrics]
- **Main Issue**: [Root cause analysis]
- **Files Affected**: [List specific files]

## REMAINING WORK

### 1. [Priority Task Name] (Priority N)

- **Problem**: [Specific technical issue]
- **Current Error**: [Exact error messages]
- **Solution Approach**: [Concrete implementation steps]
- **Files to Modify**: [Specific file paths]

## TECHNICAL CONSTRAINTS

- **CRITICAL**: [Non-negotiable requirements]
- **Framework**: [Technology stack requirements]
- **Dependencies**: [Package/version constraints]

## WHAT NOT TO DO

- [Explicit forbidden actions with reasoning]

## WHAT TO DO

- [Explicit required actions with priority]

## SUCCESS CRITERIA

[Measurable outcomes with acceptance criteria]
```

---

## Data Preprocessing S.M.A.R.T. Example

```markdown
ROLE: You are a Senior Python Developer specializing in data preprocessing, pandas,
scikit-learn, and reproducible data pipelines for the M.Sc. DSAI learning workspace.

MISSION: Add a preprocessing notebook for Week 03 (Data Quality and Issues) in
t1-data-preprocessing - load a sample dataset, detect missing values and outliers,
apply cleaning steps, and document why each step is applied.

AUDIENCE: Swamy PKV (personal learning workspace) with:
- Basic Python, pandas, and Jupyter
- Familiarity with data quality concepts (MCAR, MAR, MNAR)
- Interest in reproducible preprocessing for ML

RESPONSE FORMAT:
- Jupyter notebook: weeks/weekN/04_notebook.ipynb naming
- Markdown cells explaining the preprocessing concept before code
- Clear flow: Context -> Data setup -> Clean/Transform -> Validate -> Reflect
- Comments explaining the *why* of each preprocessing step
- Reproducible (seeds, pathlib, no hardcoded paths)

TASK CONSTRAINTS:
- CRITICAL: Zero-copy policy - original synthesis only
- CRITICAL: No hardcoded absolute paths (use pathlib/relative)
- Seven-layer week companions (DPP): reading-notes -> examples -> quizzes ->
 notebooks -> model-papers -> discussion-prompts -> assignments (aligned XX_ + slug; weeks on demand)
- Tech Stack: Python 3.12+, pandas, scikit-learn, matplotlib, seaborn, Jupyter
```

---

## Effective Instruction Patterns

### DO — Be Specific and Explicit

- "Add a preprocessing notebook for week 03 covering outlier detection with IQR and Z-score"
- "Update `weeks/week2/03_quiz.md` to add five new original multiple-choice questions"
- "Fix broken cross-references in week 04's seven companion files under `weeks/week4/`"

### DON'T — Be Vague

- "Fix the notebook"
- "Make it work"
- "Update the content"

### Strong Constraint Language That Works

```markdown
CRITICAL: Zero-copy policy — original synthesis only; no copy-paste from source material.
CRITICAL: Do not modify, overwrite, or delete anything in source-material/.
CRITICAL: All seven layers for a week must share the same XX_ prefix and topic slug.
```

### Weak Language That Doesn't Work

```markdown
Please try to keep notes original.
Prefer maintaining the naming convention.
```

---

## Prompt Design Patterns

### Multi-Layered Prompt Architecture

```markdown
SYSTEM LAYER:
You are a [Specialist Role] with expertise in [Technology Stack] and [Domain Expertise].

CONTEXT LAYER:
[Project context, current situation, repository conventions]

TASK LAYER:
[Specific implementation task with clear deliverables]

SPECIFICATION LAYER:
[Detailed technical requirements, constraints, and acceptance criteria]
```

### Progressive Refinement Pattern

```markdown
BASE PROMPT: [Core role and task definition]
REFINEMENT 1: Add specific technical constraints
REFINEMENT 2: Define output format requirements
REFINEMENT 3: Include quality standards and acceptance criteria
FINAL VALIDATION: Ensure all constraints are explicitly stated
```

---

## Data Preprocessing Integration Checklist

### Repository Development

- [ ] Follow seven-layer week companion architecture (DPP only)
- [ ] Use first-person learning journey voice (zero-copy policy)
- [ ] Define concepts before code; use LaTeX for formulas where relevant
- [ ] Verify seven-layer parity across all layers in `weeks/weekN/`

### Notebooks (preprocessing experiments)

- [ ] Naming: `weeks/weekN/04_notebook.ipynb`
- [ ] Flow: Context -> Data setup -> Cleaning/transformation -> Validation -> Reflection
- [ ] Comment the *why* of each preprocessing step; use pandas/scikit-learn
- [ ] Random seeds set; no hardcoded paths

### Examples and Quizzes

- [ ] Worked examples in `weeks/weekN/02_examples.md`
- [ ] Quizzes in `weeks/weekN/03_quiz.md`
- [ ] Original scenarios and questions only; cite specific definitions

### Quality Validation

- [ ] `uv run black --check src/` and `uv run isort --check-only src/` pass
- [ ] Notebook JSON parses successfully
- [ ] Markdownlint passes on configured globs
- [ ] No `source-material/` references in public docs
- [ ] Seven-layer parity for all in-scope weeks

---

## Best Practices Summary

1. **Be Specific**: Define exact roles, technologies, and constraints
2. **Set Clear Boundaries**: Use strong constraint language
3. **Define Success**: Include measurable outcomes and validation steps
4. **Control Output**: Specify exactly what format and quality you expect
5. **Validate Everything**: Include CI-aligned build and lint requirements
6. **Align with Architecture**: Reference seven-layer week companion model
7. **Document Thoroughly**: Ensure all decisions and constraints are recorded

---

**Related**: `.github/copilot-instructions.md`, `.cursor/rules/09_week-companion-architecture.mdc`, `.github/skills/`
