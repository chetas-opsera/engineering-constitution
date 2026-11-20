# Engineering Constitution

**Maximum engineering value. Minimum implementation complexity. Zero unjustified complexity.**

A persistent, reusable **Engineering Constitution** for AI-assisted software work — usable with **any** coding agent (Cursor, Claude Code, Copilot, Windsurf, Aider, Continue, Codex, Gemini CLI, custom agents).

| | |
|---|---|
| **Version** | 1.0.0 (2026-11-20) |
| **License** | MIT |
| **Core skill** | [`SKILL.md`](./SKILL.md) |
| **Philosophy** | Maximum output with minimum code — not code golf |

---

## Why this exists

AI coding sessions drift: overbuilt abstractions, duplicate logic, silent contract breaks, skipped tests, kitchen-sink diffs. This repo is a **single source of truth** so every agent session follows the same engineering law.

**Final principle**

> MAXIMUM ENGINEERING VALUE.  
> MINIMUM IMPLEMENTATION COMPLEXITY.  
> ZERO UNJUSTIFIED COMPLEXITY.

**Core philosophy**

> MAXIMUM OUTPUT WITH MINIMUM CODE.

Never sacrifice readability, reliability, security, or correctness to reduce line count. Optimize for **minimum total system complexity**, not minimum LOC.

---

## Three-layer rule system

```
┌─────────────────────────────────────────────────────────┐
│  Layer 1 — Global constitution (always)                 │
│  SOLID · KISS · DRY · YAGNI · Security · Simplicity     │
│  → SKILL.md                                             │
├─────────────────────────────────────────────────────────┤
│  Layer 2 — Tech standards (load only what you touch)    │
│  → standards/{architecture,backend,frontend,...}.md     │
├─────────────────────────────────────────────────────────┤
│  Layer 3 — Task execution (scale to task size)          │
│  → templates/ + checklists/                             │
└─────────────────────────────────────────────────────────┘
```

Do **not** dump the entire constitution into every prompt. Keep Layer 1 always loaded; open Layer 2–3 only when relevant.

---

## Quick start (any AI agent)

### Option A — System / project instructions (universal)

1. Copy or clone this repo next to your project (or submodule it).
2. Point your agent’s **always-on instructions** at [`SKILL.md`](./SKILL.md) (see [adapters/](./adapters/)).
3. Tell the agent: *“Follow the Engineering Constitution in `engineering-constitution/SKILL.md`. Load `standards/*` only for domains you touch.”*

### Option B — One-shot prompt prefix

Paste at the start of a session (or into a custom instruction field):

```text
You must follow the Engineering Constitution (Maximum Output With Minimum Code).
Before coding: inspect existing architecture, reuse before rebuild, plan the
smallest safe change. Apply SOLID, KISS, DRY, YAGNI. Security by default.
No unnecessary deps/abstractions. Run relevant tests before claiming done.
Scale process to task size. Full rules: <path-or-URL>/SKILL.md
```

### Option C — Cursor Agent Skill

```bash
git clone https://github.com/chetas-opsera/engineering-constitution.git \
  ~/.cursor/skills/engineering-constitution
```

Enable the always-on rule from [`adapters/cursor/engineering-constitution.mdc`](./adapters/cursor/engineering-constitution.mdc) in your project’s `.cursor/rules/`.

---

## Install adapters (per agent)

| Agent | Adapter | What to do |
|-------|---------|------------|
| **Any / custom** | [`adapters/universal/AGENTS.md`](./adapters/universal/AGENTS.md) | Copy into repo root `AGENTS.md` or merge the “Always load” block |
| **Cursor** | [`adapters/cursor/`](./adapters/cursor/) | Skill dir + always-on `.mdc` rule |
| **Claude Code** | [`adapters/claude-code/CLAUDE.md`](./adapters/claude-code/CLAUDE.md) | Merge into project `CLAUDE.md` or `~/.claude/` instructions |
| **GitHub Copilot** | [`adapters/copilot/copilot-instructions.md`](./adapters/copilot/copilot-instructions.md) | Use as `.github/copilot-instructions.md` |
| **Windsurf** | [`adapters/windsurf/`](./adapters/windsurf/) | Cascade / workspace rules snippet |
| **Aider** | [`adapters/aider/CONVENTIONS.md`](./adapters/aider/CONVENTIONS.md) | Point `--read` or project conventions at this file + `SKILL.md` |
| **Continue.dev** | [`adapters/continue/`](./adapters/continue/) | Rules / system message snippet |
| **OpenAI Codex / ChatGPT** | [`adapters/openai/`](./adapters/openai/) | Custom GPT / project instructions |
| **Gemini CLI / Antigravity** | [`adapters/gemini/`](./adapters/gemini/) | System instruction stub |

Canonical law stays in **`SKILL.md`**. Adapters only tell each product *where* to load it — avoid forked conflicting copies.

---

## Repository layout

```
engineering-constitution/
├── SKILL.md                 # Layer 1 — primary entry (agents load this)
├── README.md                # This file
├── LICENSE                  # MIT
├── CHANGELOG.md
├── adapters/                # Product-specific wiring (not a second constitution)
│   ├── universal/
│   ├── cursor/
│   ├── claude-code/
│   ├── copilot/
│   ├── windsurf/
│   ├── aider/
│   ├── continue/
│   ├── openai/
│   └── gemini/
├── standards/               # Layer 2
│   ├── architecture.md
│   ├── backend.md
│   ├── frontend.md
│   ├── database.md
│   ├── security.md
│   ├── performance.md
│   ├── testing.md
│   └── documentation.md
├── templates/               # Layer 3
│   ├── architecture-decision-record.md
│   ├── implementation-plan.md
│   ├── implementation-report.md
│   └── technical-review.md
├── checklists/
│   ├── session-initialization.md
│   ├── implementation-review.md
│   └── production-readiness.md
└── examples/
    ├── good-patterns.md
    └── anti-patterns.md
```

---

## Session initialization (every agent, every non-trivial task)

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

Never assume a new implementation is necessary. Never introduce a new library, framework, abstraction, service, database, or architectural pattern without justification.

---

## Self-audit (before claiming done)

Use [`checklists/implementation-review.md`](./checklists/implementation-review.md). Highlights:

- [ ] Existing architecture inspected; reuse considered  
- [ ] No unnecessary dependencies or abstractions  
- [ ] Security and performance implications reviewed  
- [ ] Relevant tests **executed** (not claimed)  
- [ ] No unrelated modifications; no secrets in the diff  

---

## Versioning

Bump the **Version** field in [`SKILL.md`](./SKILL.md) when Layer-1 rules change. Keep adapters thin so they rarely need edits. See [`CHANGELOG.md`](./CHANGELOG.md).

---

## Origin

Extracted and generalized from Forge / SoftwareForge engineering practice (Opsera). Designed to travel: one constitution, many agents.

## Contributing

PRs welcome for clearer adapters, additional agent wiring, and sharper Layer-2 standards. Keep `SKILL.md` concise — put depth in `standards/` and `examples/`.
