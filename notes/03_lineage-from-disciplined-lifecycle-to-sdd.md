# Lineage: from disciplined lifecycle to specification-driven work

I'm mapping where **specification-driven** (or spec-first) thinking fits relative to ideas I've
already seen—SDLC-style phases, heavy PRDs, test-driven habits, and old dreams of generating code
from models. This note is my own compression of that arc, not a history lesson for anyone else.

## What I'm keeping from older discipline

Structured phases taught me that **cheap clarity upfront beats expensive rework**. Even when I
reject rigid handoffs, I still want checkpoints, accountability, and explicit risk management before
I commit to large implementation swings.

## Where classic documents broke down

Big requirement documents often **lost a fight with the repo**. Once coding started, the code became
the live truth; the document aged unless someone heroically maintained it. I'm interested in methods
where the specification stays authoritative because it is wired into how we work—not because we
promised to be diligent.

## Executable intent

Test-first and behavior-driven practice showed me that **intent can drive automated checks**. That
bridged the gap between prose and something the machine enforces. I'm extending that intuition: if an
AI is doing more implementation, the specification may need to be even more explicit than what
worked for human-only teams—less room for silent inference.

## Model-driven hopes and today's generators

Model-driven ideas wanted a high-level description to compile into implementation. Tools were often
brittle. What I see now is a much more flexible *translator* role for models—still dangerous if my
intent is fuzzy, but a different tradeoff than bespoke code generators of the past.

## My working definition

For my notes, **spec-driven development** means: I maintain a detailed, binding map of behavior (and
often structure) that implementation must satisfy, and I use AI to speed mechanical steps **inside**
that map—not instead of it.

## The bottleneck I'm watching

When code synthesis gets cheap, the expensive part becomes **how clearly I think**. Typing speed and
framework trivia matter less; ambiguity hurts more. That reorders where I invest attention.
