# Session Refinement Prompt

Reflect on this session and update the project docs. Follow these steps exactly:

1. **Reflect on the session:**
   - What errors or failures occurred? How were they resolved?
   - What patterns or conventions were used or discovered?
   - What decisions were made and why?
   - What would be useful to remember next session?

2. **Discover existing docs:**
   Run `find .claude/docs -name "*.md" | sort` to see what already exists.

3. **Check doc conventions:**
   If `.claude/docs/documentation.md` exists, read it before writing anything.

4. **Update or create docs:**
   For each meaningful insight from this session:
   - Find the right existing doc to update, OR
   - Create a new doc with a self-describing name (e.g., `auth.md`, `api-patterns.md`, `db-migrations.md`)
   - Keep each doc to 5–10 lines max
   - Write patterns and gotchas, not step-by-step details
   - Prefer updating an existing doc over creating a new one

5. **Report changes:**
   List exactly what you created or updated, and one sentence explaining why each change was made.

**Doc format guidelines:**
- No intros or preamble — start with the content
- Use short bullet points
- Capture the "why" behind patterns, not just the "what"
- If a fix was non-obvious, note the root cause
