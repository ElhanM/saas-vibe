# Security

- Never log: passwords, tokens, API keys, PII, JWTs, raw webhook payloads
- Validate and sanitize all external input at entry points — internal callers can be trusted
- Least privilege: DB users, API keys, and service accounts get only what they need
- Never expose internals in client errors — log full details server-side, return a safe message
- Secrets never in code or version control — use env vars or a secrets manager
- Fail fast on missing required config at startup — don't let the app silently run in a broken state
