# Project playbook — how I reuse this repo for future work

I treat **this repository** as the place where I lock in **intent, patterns, and proof ideas** before (or
alongside) code in **separate project repositories**. The goal is a **repeatable sequence** so I do not
reinvent the workflow every time.

## What “predictable” means for me

- I can **name what “done” means** before I lean on generated code.
- I can **tell whether a change still matches intent** (checks, tests, human review — whatever fits).
- I can **find the same kinds of artifacts** in the same folders every time I start something new.

This playbook is **not** a guarantee that every project succeeds; it is a **default path** I can follow
until I have a reason to change it.

## Where work lives

| Kind of work | Where I put it in *this* repo | Where the running system usually lives |
|--------------|-------------------------------|----------------------------------------|
| Problem framing, tradeoffs, “what I learned” | `src/notes/` | N/A |
| Behavior I want, acceptance signals, prompt contracts | `src/specs/` | Project repo implements it |
| How I will know it works, metrics, golden cases | `src/evals/` | Project repo wires checks |
| Reusable moves I want to copy next time | `src/patterns/` | N/A |
| Spikes, half-finished tries | `src/experiments/` | Maybe a branch or throwaway repo |
| How *this* workspace is organized | `docs/` | N/A |

Production or product code still belongs in **other repos**, as already stated in `README.md`. This repo
stays the **thinking and specification home base**.

## Default step-by-step loop

I run these steps **in order** when I start something non-trivial. I skip or shrink steps only on purpose.

### 1. Name the outcome

- One short **outcome statement** (what exists when I am happy).
- **Non-goals** (what I am not building yet).
- **Constraints** (stack, time, compliance, latency, cost).

I usually capture this in `src/notes/` first, then promote stable parts into `src/specs/` if they become
the contract.

### 2. Write the spec before the “real” build

- **Actors / inputs / outputs** in plain language.
- **Acceptance signals** I can verify (bullets, examples, edge cases).
- If AI or LLMs are involved: **prompt contract** sketch (system rules vs user payload vs expected shape).

File home: `src/specs/NN_<slug>.md` when the behavior is meant to be binding.

### 3. Decide how I will check myself

- **Automated**: tests, linters, eval scripts, schema checks.
- **Manual**: review checklist, demo script.
- **Regression**: what I rerun when I change prompts or tools.

File home: `src/evals/NN_<slug>.md` (even if the first version is just a list of intents).

### 4. Plan tasks that map to the spec

- Break work into **small verifiable chunks** (each ties back to a spec bullet or eval).
- Note **dependencies** (data, keys, infra) so I am not surprised mid-build.

I often keep the first plan in the spec file or a short note; if it grows, I split it.

### 5. Implement in the project repository

- Generated or hand-written code lives **outside** this learning repo.
- I treat **spec violations** as bugs unless I **explicitly** revise the spec.

### 6. Verify and record

- Run the evals / checks I defined.
- If I learned a **durable trick**, I add or update `src/patterns/`.
- If something failed in an interesting way, I may log it under `src/experiments/` or `src/notes/`.

## Quick checklists (copy for each new effort)

### Before I write code

- [ ] Outcome and non-goals are written.
- [ ] Spec has checkable acceptance signals.
- [ ] I know **one** way I will prove the first slice works.

### Before I call a slice “done”

- [ ] Spec and implementation agree (or spec was updated on purpose).
- [ ] Eval / test / review path was run at least once.
- [ ] Prompt or tool settings that matter are noted (temperature, model, tool choice) if relevant.

## Grounding notes I already started

My early synthesized notes under `src/notes/` (prompt-first vs spec discipline, intent before code,
lineage, specs as contract for agents) are the **conceptual foundation** behind this playbook. When I
extend the playbook, I keep the same **spec-first, eval-aware** habit.

## When to bend this playbook

I change the sequence **on purpose** when:

- The work is pure exploration with no delivery pressure (`src/experiments/`).
- The risk is so low that a full spec would be noise (I still try to write **one** acceptance sentence).
- A client or team already mandates a different process (I map this playbook to theirs mentally).

---

If this file drifts from how I actually work, I update **this doc and `CLAUDE.md` in the same pass** so
assistants stay aligned.
