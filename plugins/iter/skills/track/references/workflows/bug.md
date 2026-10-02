# Bug Workflow

## Purpose

Track a confirmed defect and its authorized correction through completion.

## Input

Observed behavior that contradicts an expectation and its existing evidence.

## Workflow

Resume the first unmet stage. Triage includes the fix's design and plan work when
needed; it does not add separate Feature gates.

| Order | Stage | Required outcome |
| ----- | ----- | ---------------- |
| 1 | [Triage](../stages/triage.md) | Confirmed defect, diagnosis, acceptance evidence, and execution authority |
| 2 | [Implement](../stages/implement.md) | Complete fix and passing regression evidence |
| 3 | [Review](../stages/review.md) | Required review and authorized delivery evidence |
| 4 | [Complete](../stages/complete.md) | Verified authorized integrated result |

## Output

Current gate, evidence, approval state, and next transition or execution handoff.

## Rules

- Complexity does not turn a Bug into a Feature.
- Never create a Bug backlog record.
