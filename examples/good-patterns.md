# Good patterns

- Extend an existing service instead of adding a parallel one.
- Put shared derivation in `api-contracts` when BE and FE must agree.
- Thin route + tested pure function for control-plane style reads.
- Optional JSONB fields + UI `?.` guards.
- Progressive load / SWR cache for large graphs instead of blocking spinners.
