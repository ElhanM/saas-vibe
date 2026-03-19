# CLAUDE.md

## BEHAVIOR

- Be concise. Sacrifice grammar for concision.
- Do not be agreeable by default. If something seems wrong or unclear, stop and say so.
- If requirements are missing or ambiguous, ask before proceeding — not after.
- Flag bad ideas. A short "this seems off because X — confirm?" is better than silent compliance.
- Never assume. Verify.
- If an approach fails twice, stop and reassess — don't retry the same thing.

## WORKFLOW

- Read `docs/README.md` for a summary of available docs, then read only what's relevant to the task
- If anything is unclear, ask before proceeding
- For 3+ file changes, list the files and a one-line summary per file before starting
- If a task would touch more than 5 files or require more than 10 steps, pause and ask: "This is a larger task — do you want the plan in chat output, saved as a file (e.g. `plans/<slug>.md`), or skip and proceed directly?" Then act accordingly.
- **Edit files sequentially, never in parallel.** Wait for each edit to be confirmed before proceeding to the next. If an edit is rejected, fix it before touching any other file.

## VALIDATION

- Do not run lint, type checks, build, tests, or code generation after making changes
- If you would normally run one of these, stop and tell the user what to run and why — do not run it yourself
- Only run such commands if the user explicitly says to
- If the user reports a failure, fix it based on the output they provide

## PLANS

- Plans live in `plans/<slug>.md`. Use this format exactly:

  ```
  # Plan: <title>
  Status: in-progress | complete
  Last updated: <date>

  ## Goal
  <what we're building or fixing>

  ## Decisions
  <key decisions made and why — update as you go>

  ## Steps
  - [x] Step 1 — brief note on what was done
  - [ ] **← NEXT** Step 2
  - [ ] Step 3

  ## Checkpoint
  <free-form: where we stopped, current state of things, gotchas, what to watch out for>
  ```

- At session start, if a plan file is provided or referenced: read it, orient to the `← NEXT` marker and `## Checkpoint`, then proceed
- Keep only one `← NEXT` marker — on the next step to do

## MEMORY

- Do not rely on internal/implicit memory between sessions. Treat each conversation as a fresh start.
- All persistent context lives in `docs/` — check `docs/README.md` for what exists.
- Never assume you "remember" something — if it's not in the repo, you don't know it.

## RULES

- Doc filenames must be self-describing (e.g., `auth.md`, `api-patterns.md`, `conventions.md`)
- `docs/` = all project docs — both short context notes and full feature docs, readable by Claude and engineers
- DO NOT read `.claude/prompts/` — those are user-invoked templates, not workflow docs
- DO NOT re-read CLAUDE.md mid-session — read once, then follow the flow