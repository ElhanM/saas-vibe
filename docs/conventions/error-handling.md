# Error Handling

- Errors must say what failed and on what — always include resource/user IDs
- Never swallow errors silently — if intentionally ignoring, log with the reason why
- Return user-safe messages to clients; log full error details server-side
