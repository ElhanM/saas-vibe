---
name: bootstrap
description: Document a codebase from scratch by reading its structure and creating docs/ files
disable-model-invocation: true
---

Document this codebase from scratch. Follow these steps exactly:

1. **Read the project manifest:**
   Look for and read whichever exists: `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, or equivalent.
   For monorepos, also read per-package manifests (e.g., `apps/*/package.json`).

2. **Read the README** (if it exists).

3. **Identify entry points:**
   Look for `main.*`, `index.*`, `app.*`, `server.*`, or whatever the manifest points to as the start of execution.

4. **Scan the folder structure:**
   Get a high-level sense of how the project is organized. Do not read every file — just enough to understand the shape.

5. **Ask before writing:**
   If the structure is unclear or ambiguous, ask one focused question before proceeding. Do not guess.

6. **Create docs in `docs/` — capture only what can't be derived from reading the code:**
   Group docs by logical area (e.g., `docs/auth/`, `docs/payments/`). Subfolders can contain subfolders if needed. Groupings should reflect what the codebase does, not how the folders are named — folder paths change, docs shouldn't have to.

   Document:
   - Conventions and patterns actually in use (naming, error handling, auth, etc.) → `docs/conventions/`
   - Non-obvious gotchas, constraints, and the *why* behind notable decisions
   - If orientation is unavoidable, describe by durable role (e.g. "auth runs in the request middleware layer"), never by file path or name — paths and filenames drift too

   Do NOT write `overview.md` / `architecture.md` or any doc that snapshots structure, stack, or data flow — that is descriptive state that drifts and is already in the code. Never document business logic; if it lives in the code, leave it there.

   Keep every doc to 5–10 lines max.

7. **Update `docs/README.md`:**
   Add an entry for every doc created, grouped by subfolder, using the format: `- \`filename.md\` — one-line description`.

8. **Extract Claude memory:**
   Check `~/.claude/projects/` for any memory files related to this project. If found, extract anything still relevant into the appropriate `docs/` subfolder (e.g., `docs/conventions/`, `docs/auth/`) — not a separate memory folder.

9. **Report when done:**
   List every file created with a one-sentence description of what it covers.

**Doc format guidelines:**
- No intros or preamble — start with the content
- 5–10 lines max per file
- Patterns and gotchas, not exhaustive details
- Self-describing filenames only
