# Lineage: from disciplined lifecycle to specification-driven work

I'm mapping where **specification-driven** (spec-first) thinking fits relative to ideas I've already
internalized—staged lifecycles, heavy requirement docs, test-driven habits, and dreams of generating code
from models. This note is **my compression** of that arc: how past methods help, where they broke, and
what I'm trying to carry forward.

## What I'm keeping from older discipline

Structured phases taught me that **cheap clarity upfront beats expensive rework**. I still want:

- **Checkpoints** before big spends of time or money.
- **Accountability**—who agreed to what, and when.
- **Risk surfaced early** instead of discovered in integration.

Even when I reject rigid waterfall handoffs, I want the *spirit* of those gates in a lighter form.

## Where classic documents broke down

Large requirement packets often **lost to the repository**. Once coding accelerated:

- The **running system** became the social source of truth.
- The **document** aged unless someone maintained it as a second job.
- Disagreements defaulted to "the doc must be wrong."

I'm interested in setups where the specification **stays authoritative** because it is **wired into**
reviews, tests, and merges—not because we promised to be diligent.

## Executable intent (the bridge)

Test-first and behavior-driven work showed me that **intent can drive automated checks**. That turned
prose into something the machine could **enforce**, not just admire.

I'm extending that intuition for AI-heavy workflows:

- If a model fills gaps aggressively, my spec may need to be **more explicit** than what worked when
  only humans implemented.
- **Silent inference** becomes a bug class; I spell out what I once left tacit.

## Model-driven hopes and today's generators

Older model-driven ideas imagined a **high-level description** compiling to code. Tools were often
rigid or expensive, and the model drifted from reality.

Today's generators act more like a **flexible translator**. That is powerful and risky: flexible with
**fuzzy intent** means **creative wrong answers** at high speed. The lineage lesson for me is not
"generate from a model" alone—it is **govern the translation** with explicit intent and checks.

## How I stitch the lineage together

| Era / idea | Gift I keep | Failure mode I watch for |
|------------|-------------|---------------------------|
| Lifecycle discipline | Gates and risk thinking | Slowness, doc theater |
| Big PRDs | Shared vocabulary attempt | Doc rots; code wins by default |
| TDD / BDD | Executable examples | Brittle tests divorced from product language |
| Model-driven dreams | Separation of what vs how | Fragile tooling, round-trip pain |
| AI-assisted build | Speed on mechanical work | Ambiguity → silent assumptions |

## My working definition (for my own notes)

**Spec-driven development** (how I use the phrase): I maintain a **detailed, binding map** of behavior
(and often structure) that implementation must satisfy, and I use AI to speed **mechanical** steps
**inside** that map—not **instead** of it.

That definition is operational: it tells me what to file under `src/specs/` versus what belongs in
`src/notes/` or `src/experiments/`.

## The bottleneck I'm watching

When code synthesis gets cheap, the expensive part becomes **how clearly I think**. Typing speed and
framework trivia matter less; **ambiguity** hurts more. That reorders where I invest attention—toward
specs, evals, and small verifiable slices (`docs/02_project-playbook.md`).

### Personal checkpoint

Once a month, I want to ask: did I spend more time **prompting** or more time **making intent checkable**?
If the ratio is wildly skewed, I'm probably borrowing speed I'll pay back in defects.
