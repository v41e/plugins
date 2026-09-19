---
name: using
description: Use when choosing among a read-only brief, one bounded authorized run, or explicit saved-project dispatch.
---

# Using Iter

Route to the smallest matching skill.

## Input

Request, outcome, scope, and whether mutation or saved-project dispatch is
explicitly authorized.

## Workflow

| Request                                                                                       | Route                 |
| --------------------------------------------------------------------------------------------- | --------------------- |
| Current status, plan, or retrospective                                                        | `brief` mode          |
| One bounded authorized engineering run, or documentation work on selected surfaces            | `operate` mode        |
| Explicit sequential task dispatch across saved projects                                       | `orchestrate`         |
| Work-lifecycle classification or advancement when Locus is installed                          | `locus:track`         |
| Supported canonical-document creation, structural refresh, or reset when installed            | `locus:init`          |
| Durable-knowledge placement, promotion, or overlapping-guidance reconciliation when installed | `locus:distill`       |
| Cross-project discussion, comparison, interview, or proposal                                  | Remain read-only here |

Inside an `operate` run, installed Locus owns its matching lifecycle or
knowledge workflow.

1. Select the route; preserve an explicitly named valid route.
2. Orientation only ("Which mode should I use?"): return the routing record;
   do not run the selected workflow.
3. Execution requested: read the selected skill and applicable references
   completely; select references by the selected skill's stated routing
   conditions. Then act. Attached setup questions do not replace or delay the
   action.
4. For explicit dispatch across ordered saved projects, use `orchestrate`;
   preserve the caller's assignment. Otherwise keep cross-project discussion
   read-only or hand off to its owning umbrella project.

## Output

- Orientation or required handoff: **Route**, **Reason**, **Scope boundary**,
  **Mutation boundary**, and **Smallest next action**.
- Action in a valid execution context: follow the selected skill's output.

## Rules

- `using` performs no repository operations; the selected skill owns action.
- Daily, weekly, and monthly are cadences, not brief modes.
- Only `orchestrate` lists saved projects or dispatches tasks.
- Mentioning projects or existing tasks does not authorize dispatch.
- Setup is optional: no required config, automatic instruction edits, or
  maintained priorities/status database.
