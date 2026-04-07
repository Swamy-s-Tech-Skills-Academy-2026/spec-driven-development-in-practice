# Specs as the contract for AI-assisted building

I'm learning to treat clarity of intent as the main bottleneck when an agent can emit code quickly.
If I describe behavior loosely, I still get an answer—just not necessarily the one I needed. The
specification is the interface where I reduce guesswork.

## Why scattered docs failed me before

Wikis, PDFs, and ad hoc notes drift from the running system. I've been in the mode where **only the
repo felt trustworthy**, which threw away the "why." I'm experimenting with keeping intent **in the
same versioned place as code** so it can stay current by habit, not heroics.

## Executable intent (what it means to me)

"Executable" does not always mean the spec is literally code. It means the spec is **complete enough**
to drive the next artifacts: plans, tasks, prompts, or checks. If I omit scope, journeys, acceptance
criteria, data contracts, non-functionals, or integration points, I'm effectively asking the agent
to invent them.

## Ambiguity as debt

Models tend to complete the picture instead of pausing. I'm trying to **surface unknowns on purpose**
—open questions, rate limits, slow dependencies, localization—so they become tracked work instead of
silent guesses baked into output.

## Gates I'm considering

Fast wrong code is still wrong code. I want **human checkpoints** where leverage is high: approve the
spec, then the technical plan, then the task breakdown, then let implementation run. Each gate is a
chance to catch direction errors before they multiply.

## Project constitution

I'm drawn to a single, repo-local rule file (often Markdown) that states non-negotiables: logging,
testing expectations, architectural boundaries. That gives agents constraints without stifling every
detail.

## The question I'm carrying

If intent is the long-lived artifact and code is more disposable, **how well does my documentation
actually "compile"**—can another person or agent go from spec to correct behavior without mind
reading?
