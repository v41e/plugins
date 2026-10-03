# Plan Mode

## Purpose

Choose a feasible focus for the future horizon from goals and unfinished work.

## Input

Future `planning_horizon`, goals, latest decisions, unfinished work, dependencies,
and supplied implementation or review capacity. Optional historical `lookback`
provides recent progress.

## Workflow

1. Start from desired outcomes and approved work still unfinished. Reconcile
   prior recommendations with later human decisions and current tasks or PRs.
2. Compare outcomes by impact, urgency, dependencies, readiness, and uncertainty.
   Consider opportunities beyond the backlog and stopping work whose value no
   longer justifies it.
3. Recommend feasible progress, prerequisite decisions, and consequential reviews.
   Make parallel work, tradeoffs, and deferrals clear.

## Output

Recommend outcomes with why they matter now, completion criteria, supporting
evidence, known owners, and next actions. Distinguish approved work, decisions or
reviews needed, and new proposals. Recommend no new work when appropriate.

## Rules

- Observe current backlog separately from historical progress and the future
  horizon. Query past activity only within `lookback`; never query future events.
- Use supplied capacity and review policy; label assumptions instead of inventing
  budgets or limits on projects or workstreams.
