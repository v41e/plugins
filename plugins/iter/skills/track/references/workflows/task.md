# Task Workflow

## Input

Maintenance, dependencies, configuration, documentation, refactoring, or
operations that are neither a Feature nor a Bug.

## Workflow

Read only the first unmet stage's contract.

| Order | Stage | Required outcome |
| ----- | ----- | ---------------- |
| 1 | [Scope](../stages/scope.md) | Proportional contract and acceptance evidence |
| 2 | [Implement](../stages/implement.md) | Complete change and passing required checks |
| 3 | [Review](../stages/review.md) | Required review and authorized delivery evidence |
| 4 | [Complete](../stages/complete.md) | Verified authorized integrated result |

## Output

Current gate, evidence, approval state, and next transition or execution handoff.

## Rules

- Do not add Feature ideation or Bug reproduction.
- A scoping-only request ends at Scope.
