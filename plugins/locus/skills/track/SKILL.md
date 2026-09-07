---
name: track
description: Use when repository work must be classified, resumed, or synchronized through Feature, Bug, or Task phases and optional remote tracking.
---

# Track

Keep work proportional and resumable without making temporary scaffolding
canonical.

## Input

The latest human request, current repository state, nearest instructions, and
any existing work contract, approval evidence, or tracked artifacts.

## Workflow

1. Read current Git metadata, nearest instructions, and contribution policy.
   Follow explicit links first. Treat the current repository as owner when this
   evidence establishes it; use `locus:find` only when ownership or active-work
   context remains unclear.
2. Compare the newest explicit human intent and current repository state with
   tracked artifacts. If they differ materially, return to the earliest affected
   phase and update or retire stale artifacts.
3. Classify the work and read one workflow.

   | Work    | Trigger                                      | Workflow                                      |
   | ------- | -------------------------------------------- | --------------------------------------------- |
   | Feature | A capability is new or materially expanded   | [feature.md](references/workflows/feature.md) |
   | Bug     | Observed behavior contradicts an expectation | [bug.md](references/workflows/bug.md)         |
   | Task    | Maintenance is neither a Feature nor a Bug   | [task.md](references/workflows/task.md)       |

4. Follow the workflow's order and read its linked first incomplete phase.
5. When GitHub owns remote state, read the [GitHub adapter](references/platforms/github.md)
   and its current phase reference.
6. When matching Superpowers skills are installed, read the
   [Superpowers integration](references/integrations/superpowers.md) and its
   current phase reference.

7. Apply only the current phase's approved local and remote mutations.
8. Preserve the selected checkout or worktree and follow repository Git policy.
9. Stop when human approval or unavailable authority blocks the next phase.

## Output

Report the work type, phase transition, changed artifacts, approval state,
verification, and smallest next action.

## Rules

- Use only phases in the selected workflow and preserve their order and gates.
- Keep tracking and artifacts proportional to human intent and repository policy.
