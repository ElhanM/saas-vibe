---
# Plans

Plans live in `plans/<slug>.md`. Use this format exactly:

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

## Session behavior

- At session start, if a plan file is provided or referenced: read it, orient to the `← NEXT` marker and `## Checkpoint`, then proceed
- Keep only one `← NEXT` marker — on the next step to do
- Work **one step at a time**: complete the step, mark it `[x]`, move `← NEXT` to the next step, update `## Checkpoint`, then **stop and wait for the user to say to continue** — do not proceed to the next step automatically
- Use `/update-plan plans/<slug>.md` at the end of a session to update the plan file
- If something new comes up during implementation (extra file touched, design decision changed, step added or removed), update the plan immediately to reflect it — the plan must match reality, not just original intent, so future sessions aren't misled
