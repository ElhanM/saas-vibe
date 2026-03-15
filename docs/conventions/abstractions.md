# Abstractions

- Depend on interfaces, not concrete implementations — callers shouldn't know what's behind a boundary
- Inject dependencies (db, mailer, storage) — don't instantiate inside a function; makes implementations swappable without callers knowing
- External service boundaries should always be interfaces, even with one real implementation — the higher the lock-in cost or the harder it is to test without the real thing, the more critical this is; you will never run Twilio or charge a real card in a unit test
- Internal logic with one implementation doesn't need an interface — wait for a real second use case; premature abstraction is as harmful as none
- Abstract at seams likely to change or that cross I/O boundaries — not everywhere
- Keep interfaces narrow: one responsibility, only the methods callers actually use — if a caller uses 2 of 8 methods, split the interface
