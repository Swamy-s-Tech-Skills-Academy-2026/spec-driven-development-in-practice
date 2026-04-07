# Prompt-first speed versus spec discipline

I'm sorting out two different ways AI shows up in how I build things. One path optimizes for
velocity: I state what I want in natural language, iterate on the output, and the conversation
starts to double as an informal spec. The other path optimizes for durability: I nail down intent in
an explicit, reviewable specification and treat generated code as something that must match that
intent.

## Why the fast path stops scaling

When I'm only exploring, cheap mistakes are fine—I can throw prompts away. When something has to
last, the same habits create risk. I'm learning to name a few failure modes so I'm not surprised
later:

| Failure mode | What goes wrong |
|--------------|-----------------|
| Hidden assumptions | Vague prompts get interpreted; edge cases I never stated get filled in anyway. |
| Context loss | Decisions from last week do not live in the model's head; the patchwork grows. |
| Fit to my system | Generic solutions ignore how *this* repo is structured and named. |
| Weak traceability | "Why is it like this?" is hard to answer if the only artifact is the latest code. |

None of this means I should stop using AI. It means I need different guardrails when stakes go up.

## What I'm taking from spec-first thinking

I'm experimenting with treating the specification—not the generated snippet—as the thing that gets
versioned, discussed, and approved. The model's job, in that picture, is to implement or revise code
against that blueprint.

Practices I want to try consistently:

- Keep specs alongside the repo and review changes with similar care as code changes.
- Resolve ambiguity *before* I ask for a big generation step, instead of hoping the model asks me.
- Slice work into pieces I can test or verify independently.
- Hold back full auto-generation until I've actually agreed with the plan.
- Decide early what "done" means in terms of checks, not just a working demo.

## Reframing my role

I'm trying to spend more of my attention on clarifying intent—constraints, edge cases, security
expectations—and less on pretending that speed alone is progress. AI still feels like a multiplier;
the open question for me is whether I'm multiplying clear intent or multiplying guesses.
