# Global Defaults

## Python

- Default to the Conda environment `pytorch` for Python and package commands.
- For one-off commands, prefer `conda run -n pytorch ...`.
- For interactive shell work, default to `conda activate pytorch`.
- Before judging a Python module as missing, check it inside `pytorch` rather than with system `python3`.

## Git Commits

- Prefer staging only task-relevant files instead of using broad `git add .`.
- Commit messages must not be overly terse.
- Use a concise subject plus a multi-line body that lists the key behavioral/code changes and validation commands.
- The body should make clear what changed, why it changed, and how it was verified, especially for numerical, training, evaluation, or architecture changes.

## Naming & Architecture Fit

When adding or renaming files or classes, name them from the architecture
outward: identify the domain, subsystem, and single responsibility first, then
match the naming pattern of neighboring modules. Python modules should use
`snake_case`; related modules should share a clear subsystem prefix when that
improves discoverability. Class names should use PEP 8 `CapWords`, avoid
underscores, stay concise, and describe the object's role directly. Avoid vague
names such as `core`, `utils`, `helper`, `manager`, or `system` unless the
module or class defines a clear architectural boundary and its responsibility is
documented.
