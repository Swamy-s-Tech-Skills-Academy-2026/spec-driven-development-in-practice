# Intent before code: the inversion I'm internalizing

I've spent years in a world where **running behavior** quietly overruled documents. When docs and code
disagreed, I assumed the docs were stale. I'm learning a different default: if we have an **agreed**
specification, **code that diverges is what needs to catch up**, not the other way around—unless we
**deliberately** change the spec.

That shift is what I mean by "power inversion": authority moves from "whatever the binary does" to "what
we said it should do," with code as the servant of intent.

## A mental model that helped

I picture a **blueprint** and a **build**. If the build misses the wall placement, I don't edit the
blueprint to match the mistake; I fix the build. Software deserves the same discipline when the spec
is real, current, and **owned**—not a PDF from last year nobody reads.

The inversion breaks down if the spec is fantasy: then I'm not doing intent-first engineering, I'm
doing wishful documentation. So "spec wins" only works when the spec is **credible**.

## What makes a spec "real" instead of decorative

For me, a spec stops being shelf-ware when two things are true:

1. **Shared language** — People who matter can point at the **same sentences** about behavior without
   talking past each other. If only one person understands the doc, it is not yet a contract.
2. **Executable checks** — Examples, tests, or automated checks tie statements to something that
   **fails** when behavior drifts. Without that, the spec is a story, not a guardrail.

When those hold, code feels less like the sole authority and more like an output produced *after* intent
is clear.

## "Done" before vs after inversion

| Old default (code-first truth) | Intent-first default |
|-------------------------------|----------------------|
| Done = merged + demo works | Done = intent approved + checks green + code matches |
| Docs updated "if we have time" | Spec change is part of the same change set when behavior shifts |
| Debugging starts from "what does it do?" | Fix starts from "what did we agree it should do?" |

This connects directly to how I want to run new projects: see step 6 in `docs/02_project-playbook.md`
(verify and record).

## How I'd handle a familiar bug class

Take **"user can spam forgot-password emails."** The habit I'm trying to break is patching only in code.
The habit I'm building is:

1. State the **rate-limiting rule** in the spec (or API contract).
2. Align tasks and tests with that rule.
3. Implement.

Then the next reader sees **why** the throttle exists without spelunking. The bug fix becomes a **spec
repair** plus code, not only a code patch.

## Worked example (fictional): Acme Tasks

**Setup:** I imagine a small SaaS called **Acme Tasks** (made up; any resemblance to real products is
accidental).

**Bug:** QA says a user can hit "Forgot password" dozens of times in a minute and flood their inbox.

**Code-first reflex I am trying to unlearn:** I slap a counter in the handler, open a PR, close the
ticket. The wiki still says nothing about rate limits. Six months later someone refactors the route,
drops the counter by mistake, and **no test shouts** because behavior was never written down as intent.

**Intent-first path:** I add plain-language rules to the **spec** first: how many emails per window, what
the user sees when limited (still a generic success to avoid account enumeration), what gets logged. I
add a **check**—even one integration or contract test—that fails until the code matches. From then on,
**code is wrong if it drifts**; the spec is the anchor unless we consciously change product policy.

The spec-shaped bullets and gate order for this same slice live in
[`04_specs-as-contract-for-ai-agents.md`](./04_specs-as-contract-for-ai-agents.md).

## Longer-term reasons I care

- The **what** often outlives the **how**; clear intent should survive stack churn.
- Migrations get easier when behavior is specified **independently** of today's framework.
- Security and compliance expectations belong in **intent**, not as a late checklist.

## Small steps I'm willing to take

- Specs live **next to** implementation and get review.
- If spec and implementation disagree, treat that as a **defect** unless we explicitly revised the spec.
- Non-trivial behavior gets **testable examples** in or next to the spec.
- Work stays in **small verifiable chunks** so "spec violated" shows up fast.

## Tension I'm honest about

Intent-first can feel slower on day one. I'm trading **early friction** for **fewer silent wrong
answers** later. For me that trade is worth it when the feature touches auth, money, or data I cannot
afford to mishandle.

The question I'm sitting with: am I mostly **reacting** to whatever the code happens to do, or is the
code in service of **clarified intent** I can defend?
