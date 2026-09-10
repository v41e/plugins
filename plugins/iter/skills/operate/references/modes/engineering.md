# Engineering Mode

## Input

Require a concrete authorized change or authorized maintenance pass with a
caller-defined scope or budget. Use current code and tests, actionable open
Issues, approved unfinished specs or plans, active PRs or tasks, and relevant
workflow attempts.

## Workflow

1. For a maintenance pass, discover failed workflows, actionable open Issues,
   and approved unfinished work. Deduplicate candidates before acting. A
   healthy repository is a verified no-op.
2. Reconcile every candidate with current code, active ownership, and newer
   workflow attempts for the same workflow, branch, and commit.
3. Record a superseded failure as skipped and continue with the remaining
   candidates. Supersession ends only that candidate, never the whole pass.
4. For the next unresolved, authorized, unowned candidate, establish the change:
   - For a defect, reproduce it with the narrowest relevant command and trace
     the failing path and its callers to the shared root cause.
   - For additive work, use the approved acceptance criteria and inspect the
     affected paths and callers. Capture a focused failing acceptance check
     when the requested behavior is executable.
5. Implement the smallest complete change inside the authorized scope.
6. Add or update the smallest durable check for the defect or acceptance criteria.
7. Run focused checks, then repository-required broader checks.
8. Default to one independently reviewable outcome. Continue to another
   candidate only when the caller's explicit scope or budget includes it.
9. Deliver through the permitted Git and PR workflow.

## Output

Report the defect's reproduced cause or the additive work's acceptance results,
changed files, tests and checks with results, delivery state, skipped superseded
or owned candidates, remaining blockers, and human action.

## Rules

- Implement only requested or explicitly approved changes, or reproducibly
  necessary fixes inside the authorized pass.
- Do not duplicate work already owned by an active task or PR.
- Preserve unrelated dirty-worktree changes.
- Do not broaden a fix into speculative cleanup or an unapproved refactor.
- A maintenance pass is bounded; it is not permission to fix every discovered
  issue in one change.
