---
name: brief
description: Use when preparing a read-only status brief, focus plan, or retrospective from current project context.
---

# Brief Current Work

Turn project evidence into useful judgments about outcomes and decisions.

## Input

- Scope, available direction, constraints, and relevant prior decisions.
- Selected modes and explicit or relative windows below.
- Caller or runtime IANA timezone and one captured `as_of`.

| Mode            | Windows                                                   | Reference                                             |
| --------------- | --------------------------------------------------------- | ----------------------------------------------------- |
| `status`        | Historical `status_window`                                | [status.md](references/modes/status.md)               |
| `plan`          | Future `planning_horizon`; optional historical `lookback` | [plan.md](references/modes/plan.md)                   |
| `retrospective` | Historical `retrospective_window`                         | [retrospective.md](references/modes/retrospective.md) |

Daily, weekly, and monthly are cadences, not modes. For unattended runs, report
missing required inputs instead of guessing or waiting indefinitely.

## Workflow

1. Read the selected modes, project instructions, and linked context: purpose,
   ownership, canonical docs, and relevant task or conversation history.
   Establish each local Git root and its contribution policy; non-Git contexts
   are valid.
2. Resolve windows against `as_of` in the supplied timezone, respecting calendar
   boundaries and daylight-saving changes. Filter historical events using exact
   UTC bounds `start <= event < end`; keep future horizons separate.
3. Gather relevant local, remote, task, and worktree evidence across the requested
   scope. Use the [GitHub adapter](references/platforms/github.md) for GitHub and
   the [Superpowers integration](references/integrations/superpowers.md) for its
   artifacts. Inspect Git status and historical commit timestamps when relevant.
4. Reconcile evidence with prior decisions and stated direction. Account for
   every requested project, concentrating investigation where uncertainty could
   change the recommendation. Continue supported analysis when context is missing.

## Output

Explain what the evidence means for the caller's goals and decisions, with
supporting links. Make the time period and material coverage limits clear.
Choose the structure and depth for the audience; distinguish facts, inferences,
and proposals without requiring a fixed report template.

## Rules

- Remain read-only in the current task: no file, Git, remote, task, schedule, or
  live-system mutations, including task creation or continuation.
- Report missing, inaccessible, or truncated evidence as **Unknown** or
  **Partial** for the affected conclusions.
- Distinguish interval activity from current state observed at collection time;
  a dirty file or today's backlog does not establish historical activity/state.
- Approval requires explicit evidence, not artifact existence or status.
  Proposals do not authorize work; preserve existing approvals and ownership.
- Human attention means an evidenced decision or reserved review. Do not infer
  commitments, release, deployment, or impact from activity alone.
