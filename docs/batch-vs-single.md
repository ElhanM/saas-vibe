# Batch vs Single Operations

- Implement single when that's what's needed — don't build batch on speculation
- When batch arrives later, replace the single — don't add alongside it; two entrypoints for the same operation become dead code neither person owns
- Don't batch operations with complex per-item side effects or branching business logic without discussion — single may be the right primitive
- Batch ≠ unbounded: a batch has a defined size ceiling; list endpoints paginate
