# Status Mode

## Input

Use the normalized historical `status_window`, `as_of`, current open state, and
the requested audience or cadence.

## Workflow

1. Separate current open Issues and PRs from activity completed in the window.
2. Identify completed changes, active work, failures, review requests, and
   decisions from verified evidence.
3. Reconcile each failure with newer attempts for the same workflow, branch,
   and commit.
4. Reserve human review and decisions for verified approval, review, or choice
   gates. Keep autonomous investigation under failures or next action.
5. Select one evidence-backed next action. Recommend nothing when the verified
   state is healthy and no decision is due.

## Output

Use six sections: **Completed**, **Active**, **Failures**, **Human review**,
**Decisions**, and **Next action**. Use `None verified`, `Unknown`, or `Partial`
explicitly.

## Rules

- Prefer identifiers and links for Issues, PRs, runs, and releases.
- Keep interval activity separate from current state at its observation time.
- A successful newer attempt supersedes an older failure only when workflow,
  branch, and commit identity match.
- A dirty file or routine CI investigation does not by itself require human
  review.
