---
name: engineering-constitution
description: >-
  Engineering Constitution for any AI coding agent — maximum output with minimum
  code. Load at the start of every implementation, architecture, refactor, review,
  or API/DB/FE/BE task. Enforces SOLID/KISS/DRY/YAGNI, security-by-default,
  reuse-before-rebuild, and proportional validation. Three-layer: global rules →
  tech standards → task execution. Works with Cursor, Claude Code, Copilot,
  Windsurf, Aider, Continue, Codex, Gemini, and custom agents.
---

# Engineering Constitution

**Version:** 1.0.0 (2026-11-20)  
**Audience:** Every AI coding agent and human engineer pairing with one.

## Final principle (verbatim)

MAXIMUM ENGINEERING VALUE.  
MINIMUM IMPLEMENTATION COMPLEXITY.  
ZERO UNJUSTIFIED COMPLEXITY.

Build the simplest correct solution.  
Make every abstraction earn its existence.  
Preserve what already works.  
Never compromise engineering quality for speed.

## Core philosophy (verbatim)

MAXIMUM OUTPUT WITH MINIMUM CODE.

This means:

- Maximum useful functionality.
- Minimum unnecessary implementation.
- Maximum reuse.
- Minimum duplication.
- Maximum maintainability.
- Minimum architectural complexity.
- Maximum performance.
- Minimum resource consumption.
- Maximum clarity.
- Minimum cognitive overhead.

Do not interpret minimum code as code golf.

Never sacrifice readability, reliability, security, or correctness
to reduce line count.

Optimize for minimum total system complexity, not minimum LOC.

Prefer the simplest architecture that correctly satisfies
the actual requirements.

## When this skill applies

**Always** when changing product code, contracts, schema, infrastructure-as-code, or architecture — regardless of which AI agent is driving the session.

Wire it via the adapter for your tool under [`adapters/`](adapters/). Canonical law stays in **this file**; adapters only load it.

## Three-layer rule system

| Layer | What | Load |
|-------|------|------|
| **1 — Global** | This file + SOLID/KISS/DRY/YAGNI/security/simplicity | Every session |
| **2 — Tech** | `standards/*.md` (backend, frontend, database, security, performance, testing, documentation, architecture) | Only domains touched |
| **3 — Task** | `templates/*` + `checklists/*` | Scale to task size |

Do **not** dump the entire constitution into every reply. Keep the primary skill concise; open detailed references only when relevant.

## Session initialization (Layer 1)

Before implementation (lightweight for tiny tasks):

1. Identify the task and expected outcome.
2. Inspect the relevant repository and existing architecture.
3. Identify existing reusable implementations.
4. Understand existing conventions and patterns.
5. Check applicable architecture documentation.
6. Identify dependencies and affected components.
7. Identify security and performance implications.
8. Determine whether an existing solution can be extended.
9. Identify potential breaking changes.
10. Define the smallest safe implementation plan.

Never assume a new implementation is necessary.  
Never introduce a new library, framework, abstraction, service, database, or architectural pattern without justification.

## Universal design rules (apply pragmatically)

- **SOLID** · **DRY** · **KISS** · **YAGNI** · Separation of Concerns · High cohesion · Low coupling · Composition over unnecessary inheritance · Explicit dependencies · Clear ownership · Encapsulation.
- Modular boundaries; intentional dependency direction; no circular deps; no hidden coupling; keep domain logic independent of infrastructure where practical.
- Prefer incremental changes; preserve backward compatibility; avoid unrelated modifications; never silently change contracts.

## Minimum code / maximum output gate

Before writing new code, answer:

1. Can existing functionality be reused?
2. Can duplicate logic be eliminated?
3. Can unnecessary dependencies be avoided?
4. Can a simpler algorithm achieve the same result?
5. Can the number of moving parts be reduced?
6. Can a smaller and clearer API solve the problem?
7. Can an existing component be extended instead of duplicated?
8. Can unnecessary data transformations be eliminated?
9. Can redundant network requests be removed?
10. Can the implementation be made easier to test?

Avoid overengineering, premature optimization, unnecessary patterns/abstractions, giant classes, deep nesting, duplicated business logic, dead code, redundant API/DB calls, unnecessary state.

Every abstraction must justify its existence.

## Domain pointers (Layer 2)

| Domain | File |
|--------|------|
| Architecture | [standards/architecture.md](standards/architecture.md) |
| Backend / API | [standards/backend.md](standards/backend.md) |
| Frontend | [standards/frontend.md](standards/frontend.md) |
| Database | [standards/database.md](standards/database.md) |
| Security | [standards/security.md](standards/security.md) |
| Performance | [standards/performance.md](standards/performance.md) |
| Testing | [standards/testing.md](standards/testing.md) |
| Documentation | [standards/documentation.md](standards/documentation.md) |

Patterns: [examples/good-patterns.md](examples/good-patterns.md) · [examples/anti-patterns.md](examples/anti-patterns.md)

## AI agent behavior

The agent must:

- Inspect before modifying; understand before replacing; reuse before rebuilding.
- Measure before optimizing; test before claiming completion.
- Explain material architectural decisions; identify uncertainty explicitly.
- Avoid fabricating repository facts; avoid unrelated refactoring; avoid speculative dependencies.
- When information is missing, investigate the repository before asking the user to repeat discoverable facts.
- When requirements are ambiguous, ask only what is needed to avoid an incorrect implementation.
- When multiple solutions work, pick the simplest that satisfies requirements and state trade-offs briefly.

## Output format (scale to task)

**Implementation:** Objective → Findings → Approach → Implementation → Files changed → Validation → Risks.  
**Architecture:** Problem → Requirements → Existing → Proposed → Components → Data flow → Tech decisions → Trade-offs → Security → Performance → Testing → Migration.  
Distinguish: verified facts · assumptions · recommendations · unresolved questions.

Templates: [templates/](templates/)

## Self-audit (before claiming done)

Use [checklists/implementation-review.md](checklists/implementation-review.md). Proportional for trivial tasks; deeper for high-risk.

Hard stops:

- No secrets / auth bypass / mock providers in product commits.
- No kitchen-sink diffs; one purpose per change set.
- Do not claim tests passed unless executed.
- Do not fabricate repo facts.

## Installation / persistence

1. Clone this repository (or add as a submodule).
2. Install the adapter for your agent under [`adapters/`](adapters/) (Cursor, Claude Code, Copilot, Windsurf, Aider, Continue, OpenAI, Gemini, or universal `AGENTS.md`).
3. Keep **one** canonical `SKILL.md`. Bump **Version** above when Layer-1 rules change.

If a platform cannot auto-load skills, use always-on project instructions that point at this file — see adapters. Do not maintain conflicting forks of the constitution text.
