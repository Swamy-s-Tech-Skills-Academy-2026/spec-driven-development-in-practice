# Intent before code: the inversion I'm internalizing

I've spent years in a world where running behavior quietly overruled documents. When docs and code
disagreed, I assumed the docs were stale. I'm learning a different default: if we have an agreed
specification, **code that diverges is what needs to catch up**, not the other way around—unless we
deliberately change the spec.

## A mental model that helped

I picture a blueprint and a build. If the build misses the wall placement, I don't edit the
blueprint to match the mistake; I fix the build. Software deserves the same discipline when the spec
is real, current, and collectively owned.

## What makes a spec "real" instead of decorative

For me, a spec stops being shelf-ware when two things are true:

1. **Shared language** — Product and engineering can point at the same statements about behavior
   without talking past each other.
2. **Executable checks** — Examples, tests, or automated checks tie statements to something that
   fails when behavior drifts.

When those hold, code feels less like the sole authority and more like an output produced *after*
intent is clear.

## How I'd handle a familiar bug class

Take something like "user can spam forgot-password emails." The habit I'm trying to break is
patching only in code. The habit I'm building is: state the rate-limiting rule in the spec (or
equivalent contract), align tasks, *then* implement—so the next reader sees *why* the throttle exists
without archaeology.

## Longer-term reasons I care

- The "what" often outlives the "how"; clear intent should survive stack churn.
- Migrations get easier when behavior is specified independently of today's framework.
- Security and compliance expectations belong in intent, not as afterthoughts.

## Small steps I'm willing to take

- Specs live in the same repo and get review.
- If spec and implementation disagree, treat that as a defect unless we explicitly revised the spec.
- Non-trivial behavior gets testable examples.
- Work stays in small verifiable chunks.

The question I'm sitting with: am I mostly reacting to whatever the code happens to do, or is the
code in service of clarified intent I can defend?
