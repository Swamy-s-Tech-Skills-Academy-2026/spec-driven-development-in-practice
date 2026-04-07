# Specs as the contract for AI-assisted building

I'm learning to treat **clarity of intent** as the main bottleneck when an agent can emit code quickly.
If I describe behavior loosely, I still get an answer—just not necessarily the one I needed. The
**specification** is the interface where I reduce guesswork: same role a clear ticket has for a human, but
with less room for the model to "read my mind."

## Why scattered docs failed me before

Wikis, PDFs, and ad hoc notes **drift** from the running system. I fell into a mode where **only the
repo felt trustworthy**, which threw away the **why** behind changes.

I'm experimenting with keeping intent **versioned next to code**—same review habits, same PR flow—so
updating behavior and updating intent are **one habit**, not two.

## What "executable intent" means to me

**Executable** does not always mean the spec is literally code. It means the spec is **complete enough**
to drive the **next** artifacts without me improvising mid-flight:

- Plans and task breakdowns
- Prompts or tool policies
- Tests or eval scripts

If I omit **scope**, **user journeys**, **acceptance criteria**, **data contracts**, **non-functionals**,
or **integration seams**, I'm effectively asking the agent to **invent** them—and it will.

## Dimensions I try to cover (checklist for myself)

| Dimension | Question I answer in the spec |
|-----------|------------------------------|
| Scope | What is in / out for this slice? |
| Actors & flows | Who does what, in what order? |
| Data | Shapes, validation, retention, PII? |
| Failure | Timeouts, retries, user-visible errors? |
| Non-functional | Latency, cost, rate limits, accessibility? |
| Security | AuthZ, secrets, abuse cases? |

I do not need a novel every time; I need **no silent blanks** on dimensions that matter for *this*
change.

## Worked example (fictional): Acme Tasks (same slice as note 02)

The **story** (code-first vs intent-first) is in
[`02_intent-before-code-power-inversion.md`](./02_intent-before-code-power-inversion.md). Here I write what
I'd actually put in a spec file for a real project—still fictional, still mine.

### Scope

- **In:** Self-service "forgot password" email for **known workflow only** (user submits email, system
  sends reset link).
- **Out:** Admin-initiated resets, magic-link login, CAPTCHA (unless I add another spec slice).

### Behavior sketch (I'd file under `src/specs/` when building for real)

- User submits email on Forgot Password. Response is **always** the same success message (no hint whether
  the mailbox exists).
- Per **normalized email**, at most **3** reset emails per **15-minute** rolling window (I would pin the
  exact keying—email-only vs email+IP—in review; until then I tag **UNCERTAIN: rate-limit key**).
- When throttled, user still sees success; system emits an internal event or metric `reset_throttled` for
  monitoring.
- Email contains a **single-use** token with **20-minute** TTL; token invalid after successful password
  change.

### Dimensions filled for this slice

| Dimension | What I record |
|-----------|---------------|
| Security | No account enumeration via messaging; throttle abuse; single-use token. |
| Data | Token storage, hashing, invalidation rules—one paragraph, not a novel. |
| Failure | Email provider outage: **UNCERTAIN** retry vs queue until I decide with ops. |
| Non-functional | Protect shared SMTP reputation; avoid leaking internal errors to the user. |

### Gates and eval hook

- **Gates:** Spec (product + eng agree on limits and UX) → short technical plan (where throttle lives) →
  tasks (handler, mailer integration, test) → implement or generate **after** approval.
- **Eval / test:** A test that simulates four rapid submissions and asserts the mailer was invoked at most
  three times (or equivalent contract on the outbound email boundary).

This is the level of concreteness I want **before** I ask an agent to "just implement forgot password."

## Ambiguity as debt

Models tend to **complete** the picture instead of pausing. I'm training myself to **surface unknowns on
purpose**: open questions, unclear SLAs, localization, edge cases—tagged so they become **tracked work**
instead of silent guesses baked into generated output.

If I cannot tag an ambiguity, I probably have not understood the problem yet; generating code early would
be theater.

## Gates I'm considering

Fast wrong code is still wrong code. I want **human checkpoints** where leverage is high. One concrete
shape I borrow (including common slash-style steps in assistants) is **five core phases**, then **verify**:

1. **Constitution** (`/constitution`) — Project-wide principles: style, stack, testing norms so everything
   stays consistent.
2. **Specify** (`/specify`) — **What** to build; output like **`spec.md`**: user stories and functional
   requirements, not implementation yet.
3. **Plan** (`/plan`) — Technical architecture; output like **`plan.md`**: data models, service seams,
   library choices.
4. **Tasks** (`/tasks`) — Decompose the plan; output like **`tasks.md`**: small, **isolated, testable**
   units.
5. **Implement** (`/implement`) — Execute tasks inside those constraints; usually followed by automated
   checks and review.
6. **Verify** — Prove behavior against `spec.md` (and tests), not only that code merged.

Slash names are **mnemonics**; the important part is the **order** and the **artifacts**.

Each gate is a chance to catch **direction** errors before they multiply. Skipping gates is a conscious
risk call, not an accident.

```mermaid
flowchart TD
  P1["1 Constitution<br/>/constitution<br/>Principles, stack, test norms"]
  P2["2 Specify<br/>/specify to spec.md<br/>What (stories, functional reqs)"]
  P3["3 Plan<br/>/plan to plan.md<br/>Architecture, models, interfaces"]
  P4["4 Tasks<br/>/tasks to tasks.md<br/>Isolated, testable units"]
  P5["5 Implement<br/>/implement<br/>Agent or human, within constraints"]
  P6["6 Verify<br/>Tests + review vs spec.md"]
  P1 --> P2 --> P3 --> P4 --> P5 --> P6
  style P1 fill:#ffd966,stroke:#333,color:#000
  style P2 fill:#dae8fc,stroke:#333,color:#000
  style P3 fill:#dae8fc,stroke:#333,color:#000
  style P4 fill:#dae8fc,stroke:#333,color:#000
  style P5 fill:#d5e8d4,stroke:#333,color:#000
  style P6 fill:#fff2cc,stroke:#333,color:#000
```

## Project constitution

I'm drawn to a single, repo-local **rule file** (often Markdown) that states non-negotiables: logging,
testing expectations, architectural boundaries, banned patterns. That gives agents **guardrails**
without specifying every line. I treat it as the **defaults** layer; the spec is the **feature** layer.

## How this ties to my playbook

When I start a real project, I want **spec + eval** defined before I pretend the hard thinking is over—see
`docs/02_project-playbook.md` steps 2–3. This note is the **why** behind those steps when AI is in the
loop.

## The question I'm carrying

If intent is the long-lived artifact and code is more disposable, **how well does my documentation
actually "compile"?**—can another person or agent go from spec to correct behavior **without** mind
reading?

When the answer is "not well enough," my next move is to **tighten the spec**, not to blame the tool.
