# Prompt Factory

Capture any reusable pattern and write a prompt for it.

**Pattern:** [name and describe the pattern — e.g., "CRUD endpoints for a resource", "extracting inline DB queries into a repository layer", "OAuth flow for a new provider"]

**Type:** [one of: implementation | refactor | feature | integration | other]

**Source:** [specify what to use — any combination of:
- files: list them explicitly
- git diff: use `git diff` or `git diff [ref]` to see what changed
- session: use what was discussed or built in this conversation
- description: use the Pattern field above]

Follow these steps exactly:

1. **Gather context from the source(s) above:**
   Use whatever was specified. If files were listed, read them. If diff, run it. If session, reflect on what was done. If a description was given, use that. Combine all sources if multiple were specified.

2. **Identify the pattern:**
   Extract the repeatable shape — what gets created, moved, renamed, split, or wired together, and why. Ignore specifics that won't generalize (exact resource names, module names, file paths, etc.).

3. **Write the prompt file:**
   - Place it in `.claude/prompts/patterns/[short-descriptive-name].md`
   - Write it as a prompt the user will paste and edit for a new target
   - Use plain prose — no placeholder syntax. Write it so the user can read and naturally edit the specific parts before running it
   - Include: what the pattern does, what to look for or provide as input, the steps to apply it, and what a good result looks like
   - Keep it focused — enough detail to reproduce the pattern, not a tutorial

4. **Report when done:**
   State the file path created, and one sentence describing the pattern it captures.
