# S.M.A.R.T. prompt framework for coding agents

**Spec-Driven Development in Practice** — framework for writing high-quality agent instructions aligned with this Markdown learning workspace.

---

## The S.M.A.R.T. framework

```text
S — Specific role definition (e.g. SDD note author, spec reviewer)
M — Mission-critical requirements (measurable outcomes)
A — Audience-aware communication (here: personal learning, first-person)
R — Response format control (headings, tables, Mermaid, file paths)
T — Task-oriented constraints (Markdown-only repo, zero-copy, naming)
```

---

## Repository alignment

When creating prompts for this repo, consider:

- **Pattern**: instruction-following, role-based, chain-of-thought, or evaluation-style task?
- **Location**: which topic folder (`specs/`, `evals/`, `patterns/`, `notes/`, `experiments/`, `docs/`)?
- **Topic units**: files are **`NN_<slug>.md`**, folders created **on demand** — see `.cursor/rules/09_week-companion-architecture.mdc`.
- **Reusability**: can the prompt template apply to multiple future topic files without assuming fixed week numbers or code paths?

---

## Problem statement template

```markdown
## ROLE DEFINITION

You are a [specific role] helping refine [SDD concept / spec / eval design] in a Markdown-only personal learning repo.

## MISSION

[Clear objective with measurable outcomes]

## CONTEXT

[Brief situation — what exists today, what I am trying to clarify]

## CURRENT STATUS

- **Progress**: [what is already captured in which files]
- **Main gap**: [what is missing or inconsistent]
- **Files**: [concrete paths]

## REMAINING WORK

### 1. [Task] (priority)

- **Problem**: …
- **Approach**: …
- **Files to touch**: …

## CONSTRAINTS

- **CRITICAL**: Markdown-only; no new runtime code unless I explicitly ask.
- **CRITICAL**: Zero-copy — original synthesis; cite definitions.
- **CRITICAL**: Personal-learning voice; no course or tutorial framing for a general audience.
- **Naming**: `NN_<slug>.md` in the correct topic folder.

## SUCCESS CRITERIA

[Checkable outcomes — e.g. spec has acceptance checks, links resolve, markdownlint passes]
```

---

## S.M.A.R.T. example (SDD)

```markdown
ROLE: You are helping me refine a behavior spec and its eval hooks in my personal SDD notes repo.

MISSION: In specs/02_ingestion-guardrails.md (create on demand), write a spec for an LLM step
that classifies user tickets into priority buckets, including forbidden behaviors and a small
golden set of expected labels.

CONTEXT: I am exploring how tight specs reduce variance before I touch any implementation.

AUDIENCE: Myself only — first person, reflection-friendly, no “students” or generic tutorial voice.

FORMAT:
- Use ## / ### headings per repo standards.
- Include a short table of inputs vs expected outputs for the golden set.
- Call out temperature / tool choices if they affect determinism.

CONSTRAINTS:
- Zero-copy: no pasted vendor or course text.
- File naming: if this is the second spec file, use 02_ with a kebab-case slug; adjust if the folder already has numbering.
- Do not reference internal read-only staging folders in the prose.
```

---

## Effective instruction patterns

### Strong (specific)

- “Add `evals/01_regression-suite-outline.md` describing three metrics and when to rerun the suite.”
- “Tighten the acceptance criteria in `specs/01_prompt-contract-template.md` so each bullet is testable.”
- “Fix broken relative links between `notes/01_sdd-foundations.md` and `patterns/01_spec-first-pattern.md`.”

### Weak (vague)

- “Improve the docs.”
- “Make the spec better.”

### Constraint language that matches this repo

```markdown
CRITICAL: Zero-copy — original synthesis; cite sources for definitions.
CRITICAL: Swamy-only scope — do not reframe as shared courseware.
CRITICAL: On-demand files — do not create empty topic stubs.
```

---

## Integration checklist

### Repository development

- [ ] Correct topic folder for the content type
- [ ] `NN_<slug>.md` naming; no `00_`
- [ ] First-person learning voice where appropriate
- [ ] Internal links resolve

### Specs and evals

- [ ] Specs state observable success / failure
- [ ] Eval notes tie metrics or reviews to those specs
- [ ] Determinism and variance called out when relevant

### Quality validation

- [ ] `markdownlint-cli2` on globs in `ci-documentation.yml` (see **ci-checks** skill)
- [ ] No internal-only path names in public-facing Markdown

---

## Best practices summary

1. Name the folder and file pattern explicitly.
2. Separate **what** (behavior) from **how I will check it** (eval).
3. Use strong CRITICAL lines for zero-copy and personal-scope rules.
4. Prefer small, checkable edits over vague “polish everything” asks.

---

**Related:** `.github/copilot-instructions.md`, `.cursor/rules/09_week-companion-architecture.mdc`, `.github/skills/`
