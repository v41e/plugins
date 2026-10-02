---
name: brief
description: Use when preparing a read-only status brief, focus plan, or retrospective across one or more projects.
---

# Brief Current Work

Turn relevant evidence into judgments about outcomes, priorities, and decisions.

## Input

Scope, direction, constraints, prior decisions, one captured `as_of`, and the
caller or runtime IANA timezone.

| Mode | Windows | Reference |
| ---- | ------- | --------- |
| `status` | Historical `status_window` | [status.md](references/modes/status.md) |
| `plan` | Future `planning_horizon`; optional historical `lookback` | [plan.md](references/modes/plan.md) |
| `retrospective` | Historical `retrospective_window` | [retrospective.md](references/modes/retrospective.md) |

Daily, weekly, and monthly are cadences. For unattended runs, report missing
required inputs instead of guessing or waiting indefinitely.

## Workflow

1. Read the selected mode and caller's governing context: goals, latest human
   decisions, and prior briefs with responses or amendments. Separate
   recommendations from approved commitments; carry unfinished work forward.
2. Resolve calendar windows against `as_of` in the supplied timezone, including
   daylight saving. Filter historical events using exact UTC bounds
   `start <= event < end`; keep future horizons separate.
3. Screen the requested scope using compact summaries or existing task and
   tracker lists. Select meaningful changes and unresolved commitments or
   reviews; record discovery gaps. Quiet work can still require attention.
4. Verify details that could change the judgment: selected task turns, decisions,
   PRs, checks, source, or docs. Read child instructions when investigating that
   owner. Compact discovery accounts for scope; deep reads of routine work need
   an evidenced reason. Reconcile newer evidence with old failures or
   recommendations; stop when more detail would not change the brief.

Use the [GitHub adapter](references/platforms/github.md) only for GitHub evidence
and the [Superpowers artifact mapping](references/integrations/superpowers.md)
only when those artifacts are relevant. Use the [Codex evidence mapping](references/harnesses/codex.md)
for Codex project/task discovery and inspection. Supplied local evidence is valid.

## Output

Lead with the judgment, consequence for goals, and next outcome or decision.
Support material claims with links; explain tradeoffs, deferrals, periods, and
coverage. Separate discovery coverage from detailed verification; choose a
useful shape for the audience.

## Rules

- Remain read-only: no file, Git, remote, task, schedule, or live-system mutations,
  including task creation or continuation.
- Missing, inaccessible, or truncated evidence makes affected conclusions
  **Unknown** or **Partial**. Continue supported analysis.
- Distinguish interval activity from current state observed at collection time;
  today's files or backlog do not establish historical state.
- Approval requires explicit evidence. Artifact existence, status, silence, and
  prior proposals do not establish commitments or authorize work.
- Human attention means an evidenced decision or reserved review. Activity alone
  does not prove release, deployment, acceptance, or impact.
