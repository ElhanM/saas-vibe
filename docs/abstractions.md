# Abstractions

- Depend on interfaces, not concrete implementations — callers shouldn't know what's behind a boundary
- Inject dependencies (db, mailer, storage) rather than instantiating them inside a function or class
- This makes swapping implementations (real vs. stub, postgres vs. in-memory) trivial
- Abstract at seams that are likely to change or that cross I/O boundaries — not everywhere
- Don't invent an interface for something that only ever has one implementation — wait for the second
- Premature abstraction is as harmful as none — add it when the seam is real, not speculative
- Keep interfaces small and focused — one responsibility, not a grab-bag of methods
- Prefer many narrow interfaces over one wide one; callers should only see what they use
- If a caller only uses 2 of 8 methods, the interface is too broad — split it
