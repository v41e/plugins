---
name: using
description: Use when the requested engineering workflow or repository scope is unclear.
---

# Using Iter

Route to the smallest matching skill.

## Input

Request, outcome, scope, and whether task dispatch is explicit.

## Workflow

| Request                                                      | Route                     |
| ------------------------------------------------------------ | ------------------------- |
| Current status, plan, or retrospective                       | `brief` mode              |
| Authorized engineering or documentation                      | `operate` mode            |
| Explicit sequential task dispatch across saved projects      | `orchestrate`             |
| Work lifecycle or durable knowledge when Locus is installed  | Matching Locus capability |
| Cross-project discussion, comparison, interview, or proposal | Remain read-only here     |

If setup advice is requested, suggest these fields in an existing `AGENTS.md`:

| Field   | Content                               |
| ------- | ------------------------------------- |
| Project | Purpose, ownership, and scope         |
| Links   | Remote or project links               |
| Sources | Canonical docs and artifact locations |
| Policy  | Verification and delivery policy      |

1. Select the route; preserve an explicitly named valid route.
2. Orientation only ("Which mode should I use?"): return the routing record;
   do not run the selected workflow.
3. Execution requested: read the selected skill and references completely, then act.
   Attached setup questions do not replace or delay the action.
4. For explicit dispatch across ordered saved projects, use `orchestrate`;
   preserve the caller's assignment. Otherwise keep cross-project discussion
   read-only or hand off to its owning umbrella project.

## Output

- Orientation or required handoff: **Route**, **Reason**, **Scope boundary**,
  **Mutation boundary**, and **Smallest next action**.
- Action in a valid execution context: follow the selected skill's output.
- Setup advice: relevant fields only; no automatic edits.

## Rules

- `using` performs no repository operations; the selected skill owns action.
- Daily, weekly, and monthly are cadences, not brief modes.
- Only `orchestrate` lists saved projects or dispatches tasks.
- Mentioning projects or existing tasks does not authorize dispatch.
- Setup is optional: no required config, automatic instruction edits, or
  maintained priorities/status database.
