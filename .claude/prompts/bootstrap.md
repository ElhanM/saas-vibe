# Bootstrap Prompt

Document this codebase from scratch. Follow these steps exactly:

1. **Read the project manifest:**
   Look for and read whichever exists: `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, or equivalent. Note the project name, dependencies, and scripts.

2. **Read the README** (if it exists).

3. **Identify entry points:**
   Look for `main.*`, `index.*`, `app.*`, `server.*`, or whatever the manifest points to as the start of execution.

4. **Scan the folder structure:**
   Get a high-level sense of how the project is organized. Do not read every file — just enough to understand the shape.

5. **Ask before writing:**
   If the structure is unclear or ambiguous, ask one focused question before proceeding. Do not guess.

6. **Create these docs in `.claude/docs/`:**

   - `overview.md` — what the project does, tech stack, key entry points (5–10 lines)
   - `architecture.md` — folder structure, key modules, how data flows through the system (5–10 lines)
   - `conventions.md` — naming conventions, patterns used, anti-patterns to avoid based on what you see (5–10 lines)
   - One additional doc per major feature area or module, named descriptively (e.g., `auth.md`, `payments.md`, `api.md`)

7. **Report when done:**
   List every file created with a one-sentence description of what it covers.

**Doc format guidelines:**
- No intros or preamble — start with the content
- 5–10 lines max per file
- Patterns and gotchas, not exhaustive details
- Self-describing filenames only
