# Race Conditions

- Any check-then-act sequence is a TOCTOU risk: read balance → check sufficient → deduct. Use atomic operations or transactions.
- If two requests can modify the same row concurrently, decide: optimistic locking (version column + conflict retry) or pessimistic (`SELECT FOR UPDATE`)
- Prefer upserts over separate insert/update — avoids the race between "does it exist?" and "create it"
- Counters and aggregates: use atomic increments (`UPDATE SET count = count + 1`), not read-increment-write
- Ask: "what happens if this request runs twice simultaneously?" — if the answer is bad, add idempotency
- Background job claim steps must be atomic: `UPDATE … WHERE claimed_at IS NULL RETURNING *`
- Distributed systems: don't assume ordering — two events from different services can arrive out of order
