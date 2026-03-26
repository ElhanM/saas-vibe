# Code Comments

- Comments explain why, not what — the code already says what it does
- Keep comments tight and purposeful — don't restate the plan or narrate what the code is about to do
- If removing a comment loses no information, remove it
- Comment non-obvious decisions, edge cases, constraints, and tradeoffs
- Never comment what the function or method name already says
- Never reference implementation details from the conversation that produced the code — comments are for future readers, not a session transcript

## Inline vs. External Docs

- Prefer inline comments for implementation details — they live next to the code and stay in sync automatically
- External docs (README, markdown) must not duplicate structure already in code; point to the source of truth instead ("see X for full list")
- External docs for implementation should only capture what cannot be derived from reading the code: the *why*, workflows, and architectural decisions
- **Exception: interface/contract docs** (OAS, API schemas) are inherently external — they document the surface for consumers, not implementers. Maintain them best-effort; they won't drift the same way implementation docs do.