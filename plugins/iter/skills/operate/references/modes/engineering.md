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
4. For the next unresolved, authorized, unowned candidate, reproduce the
   behavior with the narrowest relevant command.
5. Trace the failing path and its callers, then fix the shared root cause inside
   the authorized scope.
6. Add or update the smallest durable regression check.
7. Run focused checks, then repository-required broader checks.
8. Default to one independently reviewable outcome. Continue to another
   candidate only when the caller's explicit scope or budget includes it.
9. Deliver through the permitted Git and PR workflow.

## Output

Report the reproduced cause, changed files, tests and checks with results,
delivery state, skipped superseded or owned candidates, remaining blockers,
and human action.

## Rules

- Implement only requested, explicitly approved, or reproducibly necessary
  fixes inside the authorized pass.
- Do not duplicate work already owned by an active task or PR.
- Preserve unrelated dirty-worktree changes.
- Do not broaden a fix into speculative cleanup or an unapproved refactor.
- A maintenance pass is bounded; it is not permission to fix every discovered
  issue in one change.
