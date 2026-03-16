# Database Patterns

- Never query inside a loop — batch fetch, then map in memory
- Indexes are a data-driven decision: flag missing ones, don't add blindly — weigh query frequency and table size against write cost
- Keep transactions short: compute outside, write inside
- Never use SELECT * — always specify columns
- Migrations must be reversible and reviewed before running — never auto-run in production
