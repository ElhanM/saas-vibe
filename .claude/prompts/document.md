# Document Feature Prompt

Write detailed documentation for a specific feature, folder, or flow.

**Target:** [describe what to document — e.g., "the auth flow", "src/payments/", "the onboarding sequence including FE integration"]

**Source:** [specify what to use — any combination of:
- files: list them explicitly
- git diff: use `git diff` or `git diff [ref]` to see recent changes
- session: use what was discussed or built in this conversation
- description: use the Target field above]

Follow these steps exactly:

1. **Gather context from the source(s) above:**
   Use whatever was specified. If files were listed, read them. If diff, run it. If session, reflect on what was done. If a description was given, use that. Combine all sources if multiple were specified.

2. **Read the template:**
   Read `docs/_template.md` to understand the expected structure.

3. **Check for an existing doc:**
   Run `find docs -name "*.md" | sort` to see if a doc already exists for this feature.
   - If yes: read it, then update it rather than replacing it.
   - If no: create a new file.

4. **Ask before writing:**
   If anything is unclear — missing context, ambiguous flow, unknown integration points — ask one focused question before proceeding.

5. **Write the doc:**
   - Place it in `docs/[feature].md` or `docs/[area]/[feature].md` for monorepos
   - Follow the template structure, but adapt sections to fit the feature
   - No line limit — write as much as the feature warrants
   - Be specific: real function names, actual data shapes, concrete examples where helpful
   - Cover the happy path, integration points, and known edge cases
   - Write for two audiences: Claude (to assist with future work) and a new engineer (to understand the system)

6. **Report when done:**
   State the file path created or updated, and a one-sentence summary of what it covers.
