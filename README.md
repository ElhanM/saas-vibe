# vibe-coding starter

A minimal scaffold that teaches Claude how to work on your project — with zero upfront documentation.

## How it works

All docs live in `docs/`, organized into subfolders by area. Claude reads `docs/README.md` to discover what's available, then reads only what's relevant to the current task.

**`docs/`** — All project docs. Short (5–10 lines), pattern-focused. Captures conventions, gotchas, architecture, and decisions. Organized into subfolders (e.g., `conventions/`, `api/`, `ui/`). Grows automatically via `refine.md`.

**`.claude/prompts/`** — Copy-paste templates you invoke manually. Claude never reads these unprompted.

---

## Starting a new project

Just start building. The `docs/conventions/` folder ships with reusable coding conventions. Project-specific docs start empty — that's fine.

At the end of your first session, paste `.claude/prompts/refine.md` to capture what was learned. Commit. Repeat.

## Adopting an existing project

1. Copy this repo structure into your project root.
2. Paste `.claude/prompts/bootstrap.md` — Claude reads your codebase and creates project-specific docs in `docs/`. It also extracts any relevant Claude memory into `docs/memory/`.
3. Review `docs/memory/` — edit or delete anything that's wrong or stale.
4. From that point on, use `refine.md` at session end.

---

## The core loop

```
Code → session end → paste refine.md → Claude updates docs/ → commit
```

## Prompts

| Prompt | When to use |
|---|---|
| `refine.md` | End of every session — captures patterns and fixes |
| `bootstrap.md` | Once — documents an existing codebase from scratch |
| `factory.md` | Anytime — captures a reusable pattern as a prompt |

---

## Claude Code memory — keep it lean

Claude Code has a built-in memory system at `~/.claude/projects/`. Files there are loaded into context on **every conversation start**, which means they **burn tokens on every session**.

If memory grows unchecked, you're paying for stale context you don't need.

**What to do:**

1. Open `~/.claude/` in your editor. Check `projects/` — each project has a path-encoded subfolder with a `memory/` dir inside.
2. Review and prune stale memory files.
3. Prefer `docs/memory/` in your repo instead — version-controlled, reviewable, no hidden token cost.
4. When bootstrapping, `bootstrap.md` will extract relevant Claude memory into `docs/memory/` for you. Review and edit after.

**Clear all Claude memory:** `rm -rf ~/.claude/projects/*/memory/`

**TL;DR:** `~/.claude/projects/` memory = hidden token cost. Keep it lean or use `docs/memory/` in git instead.
