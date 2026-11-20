# Performance standard

- Measure; do not assume. Prefer efficient structures, indexing, pagination, batching, lazy load, async.
- Cache only with a clear invalidation strategy.
- Do not optimize speculative bottlenecks at the expense of readability.
- Define targets per task (p95 latency, payload size, render budget) when relevant.
