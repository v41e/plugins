# Task Workflow

## Purpose

Track a proportional maintenance contract and its authorized delivery.

## Input

Maintenance, dependencies, configuration, documentation, refactoring, or
operations that are neither a Feature nor a Bug.

## Workflow

Resume the first unmet stage using evidence and existing discussion to settle
the problem and solution. Seek focused human agreement on unsettled material
choices. Add a spec or plan only when the work warrants it; each material
artifact follows [Review](../stages/review.md) before dependent work. This adds
no Feature approval stages; caller policy determines the human decisions.

| Order | Stage | Required outcome |
| ----- | ----- | ---------------- |
| 1 | [Scope](../stages/scope.md) | Work contract (local draft or existing Issue), problem/solution, acceptance evidence, proposed steps, and existing authority |
| 2 | [Review](../stages/review.md) (contract) | Independent contract review/corrections, applicable human scope/execution decision, and Issue synchronization when authorized |
| 3 | [Implement](../stages/implement.md) | Complete change and passing required checks |
| 4 | [Review](../stages/review.md) (change/PR) | Independent change review/checks, PR evidence when published, and required human decision under the delivery contract |
| 5 | [Complete](../stages/complete.md) | Verified authorized integrated result |

Contract corrections return to Scope, followed by Review with current evidence.
Unresolved authority holds progress at Review. Implementation corrections return
to Implement, followed by Review; materially changed scope needs focused human
agreement. Missing integrated verification remains at Complete; changed
implementation needs renewed Implement and Review evidence.

## Output

Current gate, evidence, approval state, and next transition or execution
handoff.

## Rules

- A scoping-only request ends with contract Review and its applicable scope
  decision; it does not authorize implementation.
