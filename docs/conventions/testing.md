# Testing

- Unit test pure helpers — they're fast, have no deps, and break clearly
- Integration test at I/O boundaries (db, http, queue) — don't mock what you can run locally
- Don't test implementation details; test behavior and outcomes
- A test that only passes because internals are mocked is not a safety net — it's noise
- If a function is hard to test, it's a design signal: it's doing too much or depending on too much
- Separate I/O from logic — a function that fetches data *and* transforms it can't be unit tested without hitting I/O; extract the logic into a pure function, keep I/O at the edges
- The right shape: an orchestrator calls a fetcher and passes results to a pure transformer — test the transformer in unit tests, the fetcher via integration tests
- Coverage is a floor, not a goal — 100% coverage of the wrong tests means nothing
