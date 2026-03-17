# vibe-coding starter

A minimal scaffold that teaches Claude how to work on your project — with zero upfront documentation.

## How it works

All docs live in `docs/`, organized into subfolders by area. Claude reads `docs/README.md` to discover what's available, then reads only what's relevant to the current task.

**`docs/`** — Persistent project memory. Short (5–10 lines), pattern-focused. Captures conventions, gotchas, architecture, and decisions. Organized into subfolders (e.g., `conventions/`, `api/`, `ui/`). Grows automatically via `/refine`.

**`CLAUDE.md`** — Rules and behavior for every session. Static, hand-written. Not memory.

**`.claude/prompts/`** — Copy-paste templates you invoke manually. Claude never reads these unprompted.

---

## Starting a new project

Just start building. The `docs/conventions/` folder ships with reusable coding conventions. Project-specific docs start empty — that's fine.

At the end of your first session, run `/refine` to capture what was learned. Commit. Repeat.

## Adopting an existing project

1. Copy this repo structure into your project root.
2. Run `/bootstrap` — Claude reads your codebase and creates project-specific docs in `docs/`. It also extracts any relevant Claude memory into the appropriate `docs/` subfolder.
3. Review the generated docs — edit or delete anything that's wrong or stale.
4. From that point on, run `/refine` at session end.

---

## The core loop

```
Code → session end → /refine → Claude updates docs/ → commit
```

---

## Skills (slash commands)

| Command | When to use |
|---|---|
| `/refine` | End of every session — captures patterns and fixes |
| `/bootstrap` | Once — documents an existing codebase from scratch |

## Prompts

| Prompt | When to use |
|---|---|
| `factory.md` | Anytime — fill in the template, then paste it to capture a reusable pattern as a prompt |

---

## Claude Code quick reference

**3 ways to give Claude instructions:**

| | What it is | Who triggers it |
|---|---|---|
| **Skill** | Playbook in `.claude/skills/` — if `disable-model-invocation: true`: only you invoke it via `/slash-command`; else: auto-triggered by Claude when relevant + you can still invoke via `/slash-command` | Auto or You |
| **Agent** | Specialist subagent in `.claude/agents/` — Claude delegates tasks to it, or you can ask for it by name | Both |
| **Prompt** | Ad hoc template in `.claude/prompts/` — you copy-paste and run manually | You |

**2 shortcuts:**

- **`/`** → run slash commands + built-ins (`/clear`, `/help`)
- **`@`** → add file or URL as context

**File structure:**
```
.claude/
├── skills/     → auto-triggered playbooks + slash commands
├── agents/     → specialist subagents
└── prompts/    → copy-paste templates (Claude never reads these)
CLAUDE.md       → rules + behavior for every session
docs/           → persistent project memory (grows via /refine)
plans/          → ephemeral plan files (gitignored, create/delete freely)
```

---

## Claude Code memory — keep it lean

Claude Code has a built-in memory system at `~/.claude/projects/`. Files there are loaded into context on **every conversation start**, which means they **burn tokens on every session**.

If memory grows unchecked, you're paying for stale context you don't need.

**What to do:**

1. Open `~/.claude/` in your editor. Check `projects/` — each project has a path-encoded subfolder with a `memory/` dir inside.
2. Review and prune stale memory files.
3. Prefer `docs/` in your repo instead — version-controlled, reviewable, no hidden token cost.
4. When bootstrapping, `/bootstrap` extracts relevant Claude memory into `docs/` for you. Review and edit after.

**TL;DR:** `~/.claude/projects/` memory = hidden token cost. Keep it lean and use `docs/` in git instead.
