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
2. Paste `.claude/prompts/bootstrap.md` — Claude reads your codebase and creates project-specific docs in `docs/`.
3. From that point on, use `refine.md` at session end.

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
