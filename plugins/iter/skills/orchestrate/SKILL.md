---
name: orchestrate
description: Use when the caller explicitly requests dispatching one task across an ordered list of saved projects.
---

# Orchestrate Projects

Run arbitrary work through exact project-owned tasks, one project at a time.

## Input

Require an explicit request to dispatch, create, or continue project-owned
tasks, an ordered project list, the caller's task, and applicable scope,
mutation, delivery, and production boundaries.

## Workflow

1. Read local project guidance needed to resolve project identities and
   boundaries. Do not copy umbrella instructions wholesale into task prompts.
2. At project and task operations, read the configured platform adapter:

   | Platform | Adapter                                   |
   | -------- | ----------------------------------------- |
   | Codex    | [codex.md](references/platforms/codex.md) |

3. Resolve every requested project exactly. Report missing or ambiguous
   identities; never guess.
4. Process resolved projects in caller order:
   1. Prepare one standalone task prompt that preserves the caller's work and
      adds only the project identity and applicable boundaries.
   2. Continue a task only when it clearly owns the same project and work.
      Otherwise create one only when authorized.
   3. Wait for that task alone. Continue waiting through normal timeouts while
      it runs; never start the next project early.
   4. Collect its outcome. Stop on human action, unresolved setup, interruption,
      a real blocker, or an exhausted caller or runtime budget.
5. Return the ordered aggregate, including unresolved and unstarted projects.

## Output

Report the caller task, project mappings, continued or created task references,
each outcome or blocker, unstarted projects, and any next human action.

## Rules

- Use project-owned tasks; local subagents are not substitutes.
- Discussion, comparison, interview, planning, proposal, open questions, prior
  effort, or matching idle tasks do not authorize dispatch.
- Do not scan repositories for candidates, rank projects, or replace the
  caller's task with a fixed route.
- Never edit project repositories from the umbrella task.
- Never invent identities, permissions, or execution context.
- Run one project task at a time.
- Never merge, release, deploy, schedule, or change live automations unless the
  caller's task and authorization explicitly require it.
