## Repository Structure

- Each top-level directory is one distributable skill.
- Every skill directory must contain a `SKILL.md`.
- Keep skill source content in its own directory; do not duplicate the same skill under multiple names.
- Optional assets such as `references/`, `scripts/`, and `agents/` belong inside the related skill directory.

## Update Rules

- When syncing from the local cc-switch skill inventory, preserve the local `SKILL.md` content unless the change is explicitly intended.
- Do not delete or rename existing skills as part of adding a new skill.
- Verify with `git status --short` and a simple file existence check before committing.
