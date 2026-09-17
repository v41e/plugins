# Plan Mode

## Input

Future `planning_horizon`, current work, direction, prior decisions, dependencies,
and supplied implementation and review capacity. Optional historical `lookback`
provides recent progress.

## Workflow

1. Reconcile current backlog with active tasks, PRs, and prior decisions; avoid
   duplicate assignments. Query past activity only within `lookback`.
2. Compare valuable outcomes across the scope by impact, urgency, dependencies,
   readiness, and uncertainty. Challenge priorities and consider opportunities
   beyond the backlog, including stopping work whose value no longer justifies it.
3. Shape a feasible recommendation around parallel implementation, prerequisite
   decisions, and consequential human reviews. Make tradeoffs and deferrals clear.

## Output

Recommend outcomes with why they matter now, completion criteria, supporting
evidence, known owners or PRs, and next steps. Distinguish approved work ready to
proceed, decisions/reviews needed, and new proposals. Show dependencies, parallel
work, review constraints, and what to defer. Recommend no new work when appropriate.

## Rules

- Observe current backlog separately from historical progress and the future
  horizon; never query future activity.
- Use supplied capacity and review policy; label assumptions instead of inventing
  budgets or limits on projects or workstreams.
