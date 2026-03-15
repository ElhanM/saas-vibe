# Session Refinement Prompt

Reflect on this session and update the project docs. Follow these steps exactly:

1. **Reflect on the session:**
   - What errors or failures occurred? How were they resolved?
   - What patterns or conventions were used or discovered?
   - What decisions were made and why?
   - What would be useful to remember next session?

2. **Discover existing docs:**
   Read `docs/README.md` to see what already exists.

3. **Update or create docs:**
   For each meaningful insight from this session:
   - Find the right existing doc to update, OR
   - Create a new doc in the appropriate subfolder with a self-describing name
   - Group docs by logical area, not folder path — groupings reflect what the code does, not how it's organized
   - Cross-cutting docs (conventions, patterns, shared rules) go in `docs/conventions/`
   - Never place docs at the `docs/` root (except `README.md`)
   - Subfolders can contain subfolders if needed
   - Keep each doc to 5–10 lines max
   - Write patterns and gotchas, not step-by-step details
   - Prefer updating an existing doc over creating a new one

4. **Update `docs/README.md`:**
   After creating or removing any doc, update `docs/README.md` to match — add new entries, remove stale ones. Keep entries grouped by subfolder, using the format: `- \`filename.md\` — one-line description`.

5. **Report changes:**
   List exactly what you created or updated, and one sentence explaining why each change was made.

**Doc format guidelines:**
- No intros or preamble — start with the content
- Use short bullet points
- Capture the "why" behind patterns, not just the "what"
- If a fix was non-obvious, note the root cause
