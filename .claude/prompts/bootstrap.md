# Bootstrap Prompt

Document this codebase from scratch. Follow these steps exactly:

1. **Read the project manifest:**
   Look for and read whichever exists: `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, or equivalent.
   For monorepos, read the root manifest and any per-package manifests (e.g., `apps/*/package.json`).

2. **Read the README** (if it exists).

3. **Identify entry points:**
   Look for `main.*`, `index.*`, `app.*`, `server.*`, or whatever the manifest points to as the start of execution.

4. **Scan the folder structure:**
   Get a high-level sense of how the project is organized. Do not read every file — just enough to understand the shape.
   If it's a monorepo, note the top-level packages/apps and what each one does.

5. **Ask before writing:**
   If the structure is unclear or ambiguous, ask one focused question before proceeding. Do not guess.

6. **Create docs in `.claude/docs/`:**

   **Single-repo:** create docs at the top level:
   - `overview.md` — what the project does, tech stack, key entry points
   - `architecture.md` — folder structure, key modules, data flow
   - `conventions.md` — naming conventions, patterns, anti-patterns found in existing code
   - One additional doc per major feature area (e.g., `auth.md`, `payments.md`, `api.md`)

   **Monorepo:** create a subfolder per major area, then the same set of docs inside each:
   - `api/overview.md`, `api/conventions.md`, etc.
   - `app/overview.md`, `app/conventions.md`, etc.
   - A root-level `overview.md` describing how the packages relate

   Keep every doc to 5–10 lines max.

7. **Report when done:**
   List every file created with a one-sentence description of what it covers.

**Doc format guidelines:**
- No intros or preamble — start with the content
- 5–10 lines max per file
- Patterns and gotchas, not exhaustive details
- Self-describing filenames only
