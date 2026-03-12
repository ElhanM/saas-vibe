# Capture Refactor Prompt

Capture a refactor pattern and write a reusable prompt for it.

**Refactor:** [describe the pattern — e.g., "extracting inline DB queries into a repository layer"]

**Source:** [specify what to use — any combination of:
- files: list them explicitly
- git diff: use `git diff` or `git diff [ref]` to see what changed
- session: use what was discussed or built in this conversation
- description: use the Refactor field above]

Follow these steps exactly:

1. **Gather context from the source(s) above:**
   Use whatever was specified. If files were listed, read them. If diff, run it. If session, reflect on what was done. If a description was given, use that. Combine all sources if multiple were specified.

2. **Identify the pattern:**
   Extract the repeatable shape of the refactor — what gets moved, renamed, split, or restructured, and why. Ignore specifics that won't generalize (exact file names, module names, etc.).

3. **Write the prompt file:**
   - Place it in `.claude/prompts/refactors/[short-descriptive-name].md`
   - Write it as a prompt the user will paste and edit for a new target
   - Use plain prose — no placeholder syntax. Write it so the user can read and edit the specific parts naturally before running it
   - Include: what the refactor does, what to look for in the target code, the steps to apply it, and what a good result looks like
   - Keep it focused — enough detail to reproduce the pattern, not a tutorial

4. **Report when done:**
   State the file path created, and one sentence describing the pattern it captures.
