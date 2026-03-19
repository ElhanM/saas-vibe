---
name: update-plan
description: Update a plan file based on the current session — pass the plan path as an argument (e.g. /update-plan plans/auth-refactor.md)
disable-model-invocation: true
---

**Plan:** $ARGUMENTS

Follow these steps exactly:

1. **Read the plan file** at the path above.

2. **Review this session:** Look back at what was discussed, built, or changed. Consider: which steps were completed, what decisions were made, what the current state of things is, any gotchas or blockers encountered.

3. **Update the plan file:**
   - Mark completed steps with `[x]` and a brief note (e.g. `— done: used X approach`)
   - Move the `← NEXT` marker to the next uncompleted step
   - Update `## Decisions` with anything decided this session that will affect future steps
   - Rewrite `## Checkpoint` to accurately describe where things stand now — what was just done, current state of the codebase, anything the next session needs to know before starting
   - Set `Last updated` to today's date
   - Set `Status` to `complete` if all steps are done

4. **Report:** State what changed in the plan (steps marked done, new checkpoint summary) in 2–3 lines.
