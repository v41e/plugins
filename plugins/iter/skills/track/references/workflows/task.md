# Task Workflow

## Purpose

Track a proportional maintenance contract and its authorized delivery.

## Input

Maintenance, dependencies, configuration, documentation, refactoring, or
operations that are neither a Feature nor a Bug.

## Workflow

Resume the first unmet stage. Resolve the problem and correct solution from
evidence and existing discussion, with focused human agreement on unsettled
material choices. Task does not automatically add draft, spec, or plan stages
and approvals; explicit human direction or repository policy still applies.

| Order | Stage | Required outcome |
| ----- | ----- | ---------------- |
| 1 | [Scope](../stages/scope.md) | Understood problem/solution, acceptance evidence, proportional steps, and execution/delivery authority |
| 2 | [Implement](../stages/implement.md) | Complete change and passing required checks |
| 3 | [Review](../stages/review.md) (change/PR) | Independent final-change review/checks before covered publication; concise summary, human PR review, and authorized integration |
| 4 | [Complete](../stages/complete.md) | Verified authorized integrated result |

Unresolved solution or authority remains at Scope. Implementation corrections
return to Implement, followed by Review with current evidence; materially changed
scope needs focused human agreement. Missing integrated verification remains at
Complete; changed implementation needs renewed Implement and Review evidence.

## Output

Current gate, evidence, approval state, and next transition or execution handoff.

## Rules

- A scoping-only request ends at Scope.
