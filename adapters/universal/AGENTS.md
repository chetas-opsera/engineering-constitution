# Agent route — Engineering Constitution

Paste or merge this into your repository’s `AGENTS.md` (or equivalent always-on agent instructions).

## Always load

1. **Engineering Constitution** — [`SKILL.md`](../../SKILL.md) (or clone path / submodule).
2. Project guide (`CLAUDE.md`, `ARCHITECTURE.md`, etc.) when present.
3. Layer 2 standards under `standards/` **only** for domains you touch.

## Hard rules

- Maximum output with minimum code — not code golf.
- Reuse before rebuild; smallest safe change; no kitchen-sink diffs.
- Security by default; never commit secrets or bypass auth for convenience.
- Do not claim tests passed unless they were executed.
- Scale process to task size — no bureaucracy for one-liners.

## Output

For implementation tasks: Objective → Findings → Approach → Implementation → Files → Validation → Risks.  
Distinguish verified facts, assumptions, recommendations, and open questions.
