# Immutability

- Don't mutate inputs — return new values instead; callers shouldn't have to defend against side effects
- Avoid shared mutable state; if two places can change the same object, bugs become hard to trace
- Prefer immutable data structures where the language supports it
- If mutation is necessary, keep it local and contained — never leak mutable state across boundaries
- Functions that mutate their arguments should say so explicitly in the name (e.g. `sortInPlace`)
