# Authorization

- Before every endpoint: who is allowed to call this, and under what conditions? No answer = don't implement yet
- "User is logged in" is not enough — scope access to what that user owns
- Never trust client-supplied IDs or roles — always derive from server-side session/token
- Auth checks belong in one layer (service or middleware), not scattered across the codebase
- Access levels: public (rare, be intentional), authenticated (scoped to owner), role-based (server-verified only)
