# Plan Mode

## Input

Use the normalized future `planning_horizon`, `as_of`, current open work,
approved commitments, dependencies, active tasks or PRs, and supplied capacity.
Use an optional normalized historical `lookback` only for recent progress.

## Workflow

1. Query current backlog as a live observation; do not reconstruct it at a past
   `as_of` or query events inside the future `planning_horizon`.
2. If `lookback` exists, gather completed activity only inside that historical
   interval and keep it separate from the horizon.
3. Separate approved commitments from drafts and proposals, then deduplicate
   work already represented by an active task or PR.
4. Prefer finishing approved work and removing blockers.
5. When approved work is empty, either propose one bounded improvement,
   refactor, or feature grounded in evidence, or recommend no new work. A
   proposal remains a human decision, not a commitment.

## Output

For each proposed outcome, state its concrete end state, evidence, dependency
or capacity risk, existing owner or PR, and required human decision. End with a
short recommended ordering or **No new work recommended**.

## Rules

- Never merge the historical `lookback` with the future `planning_horizon`.
- Do not turn every open item into a commitment.
- Do not treat an Issue, artifact, or Project status as approval without
  explicit evidence.
- Do not change priorities, assignments, Project fields, or task ownership.
