# Aider — Engineering Constitution

```bash
# Read constitution every session
aider --read path/to/engineering-constitution/SKILL.md \
      --read path/to/engineering-constitution/adapters/aider/CONVENTIONS.md
```

Or add to `.aider.conf.yml`:

```yaml
read:
  - engineering-constitution/SKILL.md
  - engineering-constitution/adapters/aider/CONVENTIONS.md
```

## Conventions

- Maximum output with minimum code; no unjustified abstractions.
- Reuse existing project patterns; match naming and layering.
- Prefer small, tested commits of related changes only.
- Security by default; never invent credentials.
- Ask before large refactors or new dependencies.
