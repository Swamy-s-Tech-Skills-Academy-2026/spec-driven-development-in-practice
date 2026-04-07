# Spec-Driven Development in Practice — structured audit

## Context

You are working with **spec-driven-development-in-practice**, Swamy PKV’s **personal learning** workspace for **Spec-Driven Development (SDD)** and deterministic AI system design. The repository is **Markdown-only**: notes, specs, evals, patterns, experiments, and meta-docs.

**Repository structure (topic folders, on demand):**

- `src/notes/` — theory, insights, evolving understanding
- `src/specs/` — behavior specifications, prompt contracts
- `src/evals/` — evaluation strategies, eval loop designs
- `src/patterns/` — SDD patterns and reusable practices
- `src/experiments/` — small experiments and iteration notes
- `docs/` — meta-documentation and guides
- `.github/` — workflows, prompts, skills
- `.cursor/` — Cursor rules and mirrored skills

**Naming:** files use `NN_<slug>.md` (two-digit prefix, kebab-case). Never `00_`. Full contract: `.cursor/rules/09_week-companion-architecture.mdc`.

**Primary objective:**
Perform a structured audit using this repo’s standards. Verify Markdown quality, topic-folder fit, zero-copy and voice, internal links, and produce actionable suggestions.

---

## Verification checks

### A. File content and structure

- Markdown heading hierarchy and fenced code language tags where used.
- Content fits the folder’s purpose (spec vs note vs eval, etc.).
- No stub files for topics not yet started.

### B. Topic unit architecture

- Files that exist follow `NN_<slug>.md` in the correct topic folder.
- On demand: do not require files for topics not present in the tree.
- Authority: `.cursor/rules/09_week-companion-architecture.mdc` and `.github/copilot-instructions.md`.

### C. Naming conventions

- Two-digit prefixes; kebab-case slugs; no `00_` (see `.cursor/rules/07_file-naming-conventions.mdc`).

### D. Content quality

- SDD concepts explained before dense jargon or diagrams.
- First-person learning voice; no instructor or “course” framing.
- Zero-copy: flag text that looks like uncited close paraphrase of external sources.

### E. Cross-references and links

- Internal links resolve.
- No references to internal-only staging material in public docs (see `.cursor/rules/06_source_material_rules.mdc`).

---

## Deliverables

1. Summary of compliance with repository structure and naming.
2. List of issues (file path, severity, description, suggested fix).
3. Up to three clear next steps to improve the repository.

---

## Behavioral expectations

- **Personal-learning focus:** clarity and honest uncertainty are fine; avoid authoritative third-person reference tone.
- **Zero-copy:** flag direct copy or thin rephrase without citation.
- **SDD lens:** specs should be testable in principle; eval content should say how success would be observed.
