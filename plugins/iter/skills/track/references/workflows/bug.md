# Bug Workflow

## Input

Observed behavior that contradicts an expectation and its existing evidence.

## Workflow

Read only the first unmet stage's contract.

| Order | Stage | Required outcome |
| ----- | ----- | ---------------- |
| 1 | [Triage](../stages/triage.md) | Confirmed defect, diagnosis, and acceptance evidence |
| 2 | [Implement](../stages/implement.md) | Complete fix and passing regression evidence |
| 3 | [Review](../stages/review.md) | Required review and authorized delivery evidence |
| 4 | [Complete](../stages/complete.md) | Verified authorized integrated result |

## Output

Current gate, evidence, approval state, and next transition or execution handoff.

## Rules

- Complexity does not turn a Bug into a Feature. Keep optional design notes and
  plans inside Triage when risk warrants them; never add Feature stages.
- Never create a Bug backlog record.
