# Simplicity

- If an implementation is hard to describe in plain language, the design is wrong
- If a solution feels convoluted, stop and discuss before implementing
- Abstract only when real duplication exists — not for hypothetical future needs
- Prefer readable code over clever code — avoid language tricks and implicit behavior that require deep familiarity with the language or framework to understand; clever code is a liability
- If a function does something surprising, it's either named wrong or doing too much
- Keep functions small — if you need to scroll to read one, it should be split
- A function should do one thing; if you find yourself writing "and" to describe it, split it
