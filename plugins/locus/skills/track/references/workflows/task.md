# Task Workflow

## Input

Use for maintenance, dependencies, configuration, documentation, refactoring,
or operations that are neither a new capability nor incorrect behavior.

## Workflow

Resume the first incomplete stage; read its contract before continuing.

| Order | Stage                               | Purpose                                     |
| ----- | ----------------------------------- | ------------------------------------------- |
| 1     | [Scope](../stages/scope.md)         | Define the proportional work contract       |
| 2     | [Implement](../stages/implement.md) | Deliver the smallest approved change        |
| 3     | [Review](../stages/review.md)       | Review through the authorized delivery path |
| 4     | [Complete](../stages/complete.md)   | Reconcile and verify the integrated result  |

## Output

Report the current stage, approval state, verification, and next transition or
blocker under the parent skill's output contract.

## Rules

- Use only the remote tracking required by repository policy, human intent, or
  existing tracking.
- Leave tiny maintenance untracked when human intent and nearest instructions
  permit it.
- Do not add Feature ideation or Bug reproduction.
