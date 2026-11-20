# Security by default

- Least privilege; secrets in Vault/env — never commit credentials.
- Input validation; output encoding; injection defense.
- Authn/authz boundaries; never trust client authorization claims.
- Never bypass existing security controls for convenience.
- Sensitive-data minimization; safe error responses; audit sensitive ops.
- Local `AUTH_ENABLED=false` / mock AI are workstation-only — never ship in product PRs.
