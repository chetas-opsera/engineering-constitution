# Architecture standard

- Prefer established project architecture unless there is a documented reason to change.
- Clear module boundaries; dependency direction intentional; no circular deps.
- Avoid unnecessary abstractions and hidden coupling.
- Keep domain logic independent of infrastructure where practical.
- Incremental change; rollback strategy for risky migrations.
- ADR template: `../templates/architecture-decision-record.md`.
