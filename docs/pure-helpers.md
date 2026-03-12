# Pure Helpers

- Extract complex logic into helpers with no external dependencies (no db, no http, no I/O)
- Helpers may call other helpers, but never infrastructure — that boundary is strict
- The calling layer (service, handler) owns the I/O; helpers only transform data
- If a helper needs a db call to do its job, the design is wrong — pass the data in instead
- Pure helpers are unit-testable with no mocks, no setup, no teardown
- Name helpers after what they compute or decide, not where they're used
- Before writing a new helper, search the codebase — the same logic likely already exists somewhere
- Duplicate helpers are a sign no one searched first; consolidate when found
