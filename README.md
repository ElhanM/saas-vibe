# vibe-coding starter

A minimal scaffold that teaches Claude how to work on your project — with zero upfront documentation.

## How it works

Two doc layers, both auto-discovered at session start:

```
find .claude/docs docs -name "*.md" | sort
```

Claude reads only the files relevant to the current task — from either location.

**`.claude/docs/`** — Claude's working memory. Short (5–10 lines), pattern-focused. Captures conventions, gotchas, and decisions. Grows automatically via `refine.md`.

**`docs/`** — Project reference docs. Detailed feature documentation: flows, integration notes, edge cases. Useful for both Claude and future engineers.

**`.claude/prompts/`** — Copy-paste templates you invoke manually. Claude never reads these unprompted.

---

## Starting a new project

Just start building. Both doc folders start empty — that's fine.

At the end of your first session, paste `.claude/prompts/refine.md` to capture what was learned in `.claude/docs/`. Commit. Repeat.

## Adopting an existing project

1. Copy this repo structure into your project root.
2. Paste `.claude/prompts/bootstrap.md` — Claude reads your codebase and creates a starter doc set in both locations.
3. From that point on, use `refine.md` at session end.

---

## The core loop

```
Code → session end → paste refine.md → Claude updates .claude/docs/ → commit
```

## Prompts

| Prompt | When to use |
|---|---|
| `refine.md` | End of every session — captures patterns and fixes |
| `bootstrap.md` | Once — documents an existing codebase from scratch |
