# Plan Mode

## Input

Use the normalized future `planning_horizon`, `as_of`, current remote and local
work, prior decisions, dependencies, active tasks or PRs, and supplied capacity.
Use an optional normalized historical `lookback` only for recent progress. A
roadmap or milestone is useful when supplied, not required.

## Workflow

1. Query current backlog as a live observation; do not reconstruct it at a past
   `as_of` or query events inside the future `planning_horizon`.
2. If `lookback` exists, gather completed activity only inside that historical
   interval and keep it separate from the horizon.
3. Reconcile prior decisions with current remote and local work, then deduplicate
   work already represented by an active task or PR.
4. Recommend focus by project and order next actions: bugs or blockers,
   implementation-ready approved work, work needing design or planning, ideas
   needing discussion, then ongoing or deferred work.
5. When no approved next action exists, either propose one bounded improvement
   grounded in evidence or recommend no new work.

## Output

For each project, state the recommended focus and ordered actions with evidence,
dependency or capacity risk, existing owner or PR, and required human decision.
End with **No new work recommended** when appropriate.

## Rules

- Never merge the historical `lookback` with the future `planning_horizon`.
- Do not turn every open item into a commitment.
- Do not treat an Issue, artifact, or Project status as approval without
  explicit evidence.
- Do not change priorities, assignments, Project fields, or task ownership.
- Proposals are not commitments.
