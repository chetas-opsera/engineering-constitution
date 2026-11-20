# Continue.dev

Add a rule / system message (Continue “rules” or `config.json` system prompt) that includes:

```text
Follow the Engineering Constitution (SKILL.md in the engineering-constitution repo).
Maximum output with minimum code. Reuse before rebuild. SOLID/KISS/DRY/YAGNI.
Security by default. Smallest safe change. Load standards/* only when relevant.
Do not claim tests passed unless executed.
```

Optionally `@`-mention or attach `SKILL.md` in the chat context for large tasks.
