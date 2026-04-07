# Pull Request

## Description

A clear and concise description of what this PR does.

## Type of change

- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New content in topic folders (`src/notes/`, `src/specs/`, `src/evals/`, `src/patterns/`, `src/experiments/`)
- [ ] Documentation update (`README.md`, `docs/`, meta-docs)
- [ ] Formatting or lint-only (no meaning change)
- [ ] Refactor (move/rename without changing substance)
- [ ] CI / automation (`.github/`, workflows)
- [ ] Agent rules or skills (`.cursor/`, `.github/skills/`)

## Content type

- [ ] `src/notes/`
- [ ] `src/specs/`
- [ ] `src/evals/`
- [ ] `src/patterns/`
- [ ] `src/experiments/`
- [ ] `docs/`
- [ ] Repository configuration (`.github/`, `.cursor/`, `CLAUDE.md`)

## Changes made

### Files changed

- `path/to/file.md`

### Summary

Brief summary of what changed and why.

## Checklist

### Pre-submission

- [ ] Changes match the **Scope** in `README.md` (personal learning; not a production deliverable)
- [ ] Content follows `.cursor/rules/01_educational-content-rules.mdc` (zero-copy, voice)
- [ ] File references and relative links checked
- [ ] Topic files use `NN_<slug>.md` in the correct folder (see `.cursor/rules/09_week-companion-architecture.mdc`)
- [ ] Markdownlint run if I touched Markdown covered by CI

### Content quality

- [ ] Original synthesis; citations where I used specific external definitions
- [ ] No references to internal-only staging material in public docs
- [ ] Cross-references updated when I moved or renamed files

### Agent assets (if this PR touches `.github/skills/` or `.cursor/skills/`)

- [ ] `.github/skills/` and `.cursor/skills/` are **byte-identical** (see `.github/skills/README.md`)

## Related issues

Closes #(issue number)  
Related to #(issue number)

## Additional notes

Context that helps review this change.

---

**Note:** This repository is Swamy PKV’s personal Spec-Driven Development learning workspace.
