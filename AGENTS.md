# Global Defaults

## 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

## 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it - don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

##  5. Python

- Default to the Conda environment `pytorch` for Python and package commands.
- For one-off commands, prefer `conda run -n pytorch ...`.
- For interactive shell work, default to `conda activate pytorch`.
- Before judging a Python module as missing, check it inside `pytorch` rather than with system `python3`.

## 6. Git Commits

- Prefer staging only task-relevant files instead of using broad `git add .`.
- Commit messages must not be overly terse.
- Use a concise subject plus a multi-line body that lists the key behavioral/code changes and validation commands.
- The body should make clear what changed, why it changed, and how it was verified, especially for numerical, training, evaluation, or architecture changes.

## 7. Naming & Architecture Fit

When adding or renaming files or classes, name them from the architecture
outward: identify the domain, subsystem, and single responsibility first, then
match the naming pattern of neighboring modules.

