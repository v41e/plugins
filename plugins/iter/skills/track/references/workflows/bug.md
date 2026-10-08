# Bug Workflow

## Purpose

Track a confirmed defect and its authorized correction through completion.

## Input

Observed behavior that contradicts an expectation and its existing evidence.

## Workflow

Resume the first unmet stage. Confirm the defect and correct solution from
reproduction, diagnosis, evidence, and existing discussion, with focused human
agreement on unsettled material choices. Bug does not automatically add draft,
spec, or plan stages and approvals; explicit direction or repository policy applies.

| Order | Stage | Required outcome |
| ----- | ----- | ---------------- |
| 1 | [Triage](../stages/triage.md) | Confirmed defect/diagnosis, proposed correction, acceptance evidence, and execution/delivery authority |
| 2 | [Implement](../stages/implement.md) | Complete fix and passing regression evidence |
| 3 | [Review](../stages/review.md) (change/PR) | Independent final-change review/checks before covered publication; concise summary, human PR review, and authorized integration |
| 4 | [Complete](../stages/complete.md) | Verified authorized integrated result |

Unresolved defect, diagnosis, solution, or authority remains at Triage. Fix
corrections return to Implement, followed by Review with current evidence;
materially changed scope needs focused human agreement. Missing integrated
verification remains at Complete; changed implementation needs renewed Implement
and Review evidence.

## Output

Current gate, evidence, approval state, and next transition or execution handoff.

## Rules

- Complexity does not turn a Bug into a Feature.
- Never create a Bug backlog record.
