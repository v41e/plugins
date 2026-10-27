# Bug Workflow

## Purpose

Track a confirmed defect and its authorized correction through completion.

## Input

Observed behavior that contradicts an expectation and its existing evidence.

## Workflow

Resume the first unmet stage using reproduction, diagnosis, and existing
discussion to settle the correction. Seek focused human agreement on unsettled
material choices. Add a spec or plan only when the work warrants it; each
material artifact follows [Review](../stages/review.md) before dependent work.
This adds no Feature approval stages; caller policy determines the human
decisions.

| Order | Stage | Required outcome |
| ----- | ----- | ---------------- |
| 1 | [Triage](../stages/triage.md) | Work contract (local draft or existing Issue), confirmed defect/diagnosis, proposed correction, acceptance evidence, and existing authority |
| 2 | [Review](../stages/review.md) (contract) | Independent contract review/corrections, applicable human scope/execution decision, and Issue synchronization when authorized |
| 3 | [Implement](../stages/implement.md) | Complete fix and passing regression evidence |
| 4 | [Review](../stages/review.md) (change/PR) | Independent change review/checks, PR evidence when published, and required human decision under the delivery contract |
| 5 | [Complete](../stages/complete.md) | Verified authorized integrated result |

Missing defect, diagnosis, or solution evidence remains at Triage. Contract
corrections return to Triage, followed by Review with current evidence.
Unresolved authority holds progress at Review. Fix corrections return to
Implement, followed by Review; materially changed scope needs focused human
agreement. Missing integrated verification remains at Complete; changed
implementation needs renewed Implement and Review evidence.

## Output

Current gate, evidence, approval state, and next transition or execution
handoff.

## Rules

- A triage-only request ends with contract Review and its applicable scope
  decision; it does not authorize implementation.
- Complexity does not turn a Bug into a Feature.
- Never create a Bug Project draft; the repository Issue owns the remote
  contract.
