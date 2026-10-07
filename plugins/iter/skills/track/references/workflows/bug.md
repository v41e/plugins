# Bug Workflow

## Purpose

Track a confirmed defect and its authorized correction through completion.

## Input

Observed behavior that contradicts an expectation and its existing evidence.

## Workflow

Resume the first unmet stage. Triage includes the fix's separate substantive spec
and plan checkpoints internally; it does not add Feature stages.

| Order | Stage | Required outcome |
| ----- | ----- | ---------------- |
| 1 | [Triage](../stages/triage.md) | Confirmed defect/acceptance; substantive spec then plan approval and delivery authority |
| 2 | [Implement](../stages/implement.md) | Complete fix and passing regression evidence |
| 3 | [Review](../stages/review.md) | Final review/checks, covered delivery, and required human PR review |
| 4 | [Complete](../stages/complete.md) | Verified authorized integrated result |

## Output

Current gate, evidence, approval state, and next transition or execution handoff.

## Rules

- Complexity does not turn a Bug into a Feature.
- Never create a Bug backlog record.
