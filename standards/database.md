# Database standard

- Explicit ownership; correct relationships; constraints; consistent naming.
- Index for real query patterns; safe migrations; referential integrity where applicable.
- Normalize/denormalize from operational needs — not dogma.
- Prefer code-first or migration-CLI consistently; example (Forge): code-first `ensureSchema()`; `safeAddColumn` on hot tables; new JSONB fields optional.
