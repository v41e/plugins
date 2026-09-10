# Status Mode

## Input

Use the normalized historical `status_window`, `as_of`, current open state,
relevant task and worktree progress, and the requested audience or cadence.

## Workflow

1. Separate current open work from material progress completed in the window.
2. Identify active work, genuine blockers, and human approval, review, or
   decision gates from verified evidence.
3. Reconcile each failure with newer attempts for the same workflow, branch,
   and commit.
4. Reserve human attention for verified approval, review, or choice gates. Keep
   autonomous investigation with active work or blockers.
5. Select one evidence-backed next action. Recommend nothing when the verified
   state is healthy and no decision is due.

## Output

Lead with material progress and active work, followed by human attention,
blockers, and the next action when present. Omit empty sections and boilerplate;
use `Unknown` or `Partial` only where missing coverage matters.

## Rules

- Prefer identifiers and links for Issues, PRs, runs, and releases.
- Keep interval activity separate from current state at its observation time.
- A successful newer attempt supersedes an older failure only when workflow,
  branch, and commit identity match.
- A dirty file is not proof of activity in the window. Relevant task or worktree
  progress may establish active work.
- A review notification is human attention; routine autonomous investigation is
  not.
