# Backend / API standard

- Routes thin → services hold logic → repositories SQL only.
- Constructor DI; explicit dependencies; strategy/factory for externals.
- Validate input; structured errors; explicit authz; transactional integrity where required.
- Efficient DB access; avoid N+1; paginate large sets; idempotency where appropriate.
- Do not expose internals via public APIs; keep contracts predictable.
- Structured logging + observability on AI/expensive paths.
- Async for expensive workloads; fail open only when product already defines that behavior.
