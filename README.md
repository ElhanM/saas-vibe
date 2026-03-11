# vibe-coding starter

A minimal scaffold that teaches Claude how to work on your project — with zero upfront documentation.

## How it works

Knowledge lives in `.claude/docs/`. Claude discovers it automatically at session start via:

```
find .claude/docs -name "*.md" | sort
```

Docs grow organically as you work. At session end, paste `refine.md` into Claude to capture what was learned. Repeat.

- `.claude/docs/` — auto-discovered knowledge base (grows over time, stays minimal)
- `.claude/prompts/` — copy-paste templates for you to invoke manually (Claude never reads these unprompted)

---

## Starting a new project

Just start building. Docs in `.claude/docs/` don't exist yet — that's fine. They'll be created as patterns emerge.

At the end of your first session, paste `.claude/prompts/refine.md` into Claude. It will write the first docs based on what happened. Commit them. Repeat next session.

## Adopting an existing project

1. Copy this repo structure into your project root.
2. Paste `.claude/prompts/bootstrap.md` into Claude. It will read your codebase and create a starter doc set in `.claude/docs/`.
3. From that point on, use `refine.md` at the end of each session to keep docs updated.

---

## The core loop

```
Code → catch errors → note fixes → session end → paste refine.md → Claude updates docs → commit
```

That's it. No manual doc maintenance. Docs improve automatically as the project grows.
