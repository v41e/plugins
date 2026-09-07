---
name: using
description: Use when the requested engineering workflow or repository scope is unclear.
---

# Using Iter

Route to the smallest matching skill.

## Input

Identify whether the request asks for orientation or action, its outcome, and
whether the caller explicitly requests dispatching work across an ordered list
of saved projects. Mentioning several projects is not a dispatch request.

## Workflow

| Request                                                      | Route                     |
| ------------------------------------------------------------ | ------------------------- |
| Current status, plan, or retrospective for one repository    | `brief` mode              |
| Authorized engineering or documentation in one repository    | `operate` mode            |
| Explicit sequential task dispatch across saved projects      | `orchestrate`             |
| Work lifecycle or durable knowledge when Locus is installed  | Matching Locus capability |
| Cross-project discussion, comparison, interview, or proposal | Remain read-only here     |

1. Daily, weekly, and monthly are cadence, not brief modes.
2. Select the route from the table; preserve an explicitly named valid route.
3. For orientation, return the routing record below and stop.
4. For one-repository action, read the selected skill and reference, then
   continue the request under their output contract.
5. Read `orchestrate` only when the caller explicitly requests task dispatch,
   creation, or continuation across an ordered saved-project list. Carry the
   caller's task unchanged in meaning. Otherwise keep cross-project discussion
   read-only or return a handoff to the owning umbrella project.

## Output

- Orientation or required handoff: **Route**, **Reason**, **Scope boundary**,
  **Mutation boundary**, and **Smallest next action**.
- Action in a valid execution context: follow the selected skill's output.

## Rules

- `using` performs no repository operations; the selected skill owns action.
- Read the selected skill and selected reference completely before acting.
- `brief` and `operate` never list saved projects or dispatch tasks.
- Only `orchestrate` coordinates multiple saved projects.
- A discussion, interview, comparison, proposal, open question, or mention of
  existing tasks is never authorization to continue or create a task.
