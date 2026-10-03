---
name: orchestrate
description: Use when the caller explicitly requests dispatching project-owned tasks across an ordered project list.
---

# Orchestrate Projects

## Purpose

Run arbitrary work through exact project-owned tasks, one project at a time.

## Input

Require an explicit request to dispatch, create, or continue project-owned
tasks, an ordered project list, the caller's task, and applicable scope,
mutation, delivery, and production boundaries.

## Workflow

1. Resolve requested projects and their boundaries from local guidance and the
   harness's returned identities. Codex capabilities are mapped in the
   [harness adapter](references/harnesses/codex.md). Report missing or ambiguous
   owners; partial discovery cannot prove absence.
2. Process resolved projects in caller order:
   1. Prepare one standalone task prompt that preserves the caller's work,
      including any explicit delivery authorization and restrictions, and adds
      only the project identity and applicable boundaries. Do not copy umbrella
      instructions wholesale. Preserve signed-commit,
      push, and PR grants separately; newer restrictions override older grants.
      Pass requested execution settings through supported tool arguments.
   2. Continue a task only when it is unfinished and clearly owns the same
      project and assignment. An Issue or PR may corroborate identity but never
      replace the assignment match; a matching title is not identity. Otherwise
      create one only when authorized.
   3. Dispatch once and wait for that task alone. Pending setup and timeouts
      are not completion; never redispatch or start the next project early.
   4. Collect its outcome and apply the continuation rules:

      | State | Action |
      | ----- | ------ |
      | Stopped with a local blocker | Continue independent work only when authorized |
      | Dependent on blocked work | Hold |
      | Shared permission/safety failure, uncertain running state, interruption, or exhausted budget | Stop |

3. Return the ordered aggregate, including unresolved and unstarted projects.

## Output

Report the caller task, project mappings, continued or created task references,
each outcome or blocker, unstarted projects, and any next human action.

## Rules

- Discussion, proposals, prior effort, and matching idle tasks do not authorize dispatch.
- Preserve the caller's assignment and order; do not scan for candidates or rank projects.
- Use project-owned tasks; local subagents are not substitutes. Never edit child
  repositories or bypass a worker's denied action from the umbrella context.
- Never invent identities, permissions, or execution context.
- Never merge, release, deploy, schedule, or change live automations unless the
  caller's task and authorization explicitly require it.
