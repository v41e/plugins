# Superpowers Integration

Optional skill mappings for conditions observed by `operate`.

## Condition mapping

| Observed condition                                                                  | Skill                                         | Semantics                                                                         |
| ----------------------------------------------------------------------------------- | --------------------------------------------- | --------------------------------------------------------------------------------- |
| A bug or unexpected behavior is reproducible                                        | `$superpowers:systematic-debugging`           | Diagnose the root cause before editing.                                           |
| Changed behavior can be expressed by a failing executable check                     | `$superpowers:test-driven-development`        | Capture RED before implementation and keep the smallest durable regression check. |
| An approved written implementation plan is being executed in this task              | `$superpowers:executing-plans`                | Execute the existing plan; do not create one merely to add ceremony.              |
| Review feedback must be applied                                                     | `$superpowers:receiving-code-review`          | Verify feedback technically before changing the implementation.                   |
| The repository workflow reaches material pre-merge review without equivalent review | `$superpowers:requesting-code-review`         | Request bounded review; do not duplicate an equivalent gate.                      |
| Completion is about to be claimed                                                   | `$superpowers:verification-before-completion` | Re-run current evidence before making the claim.                                  |

## Integration semantics

- Apply every matching condition; this adapter does not define phase order.
- Superpowers is optional. Its absence does not weaken the selected mode's
  authorization, scope, verification, delivery, or production boundaries.
- Do not add delegation, worktrees, plans, or review ceremony unless the task
  and repository policy require them.
