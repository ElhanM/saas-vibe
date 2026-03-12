# Session Refinement Prompt

Reflect on this session and update the project docs. Follow these steps exactly:

1. **Update plan file (if one exists):**
   Run `find .claude/plans -name "*.md" 2>/dev/null | sort` to check for open plan files.
   If a plan file exists that relates to work done this session:
   - Mark each item: `[x]` done, `[-]` partial (add a one-line note on what's left), `[ ]` not started
   - Add a `## Session [date]` block at the top summarizing what shifted or was decided
   - Do NOT delete the file — leave it for the next session

2. **Reflect on the session:**
   - What errors or failures occurred? How were they resolved?
   - What patterns or conventions were used or discovered?
   - What decisions were made and why?
   - What would be useful to remember next session?

3. **Discover existing docs:**
   Run `find .claude/docs -name "*.md" | sort` to see what already exists.
   Note: docs may be organized in subfolders (e.g., `api/`, `app/`, `infra/`) — this is intentional for monorepos.

4. **Update or create docs:**
   For each meaningful insight from this session:
   - Find the right existing doc to update, OR
   - Create a new doc with a self-describing name (e.g., `auth.md`, `api/patterns.md`, `db-migrations.md`)
   - Keep each doc to 5–10 lines max
   - Write patterns and gotchas, not step-by-step details
   - Prefer updating an existing doc over creating a new one
   - If the project has distinct areas (e.g., api, app, infra), use subfolders to namespace docs

5. **Report changes:**
   List exactly what you created or updated, and one sentence explaining why each change was made.

**Doc format guidelines:**
- No intros or preamble — start with the content
- Use short bullet points
- Capture the "why" behind patterns, not just the "what"
- If a fix was non-obvious, note the root cause
