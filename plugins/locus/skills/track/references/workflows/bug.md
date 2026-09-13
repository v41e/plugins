# Bug Workflow

## Input

Use for observed behavior that contradicts an existing expectation.

## Workflow

Resume the first incomplete stage; read its contract before continuing.

| Order | Stage                               | Purpose                                            |
| ----- | ----------------------------------- | -------------------------------------------------- |
| 1     | [Triage](../stages/triage.md)       | Confirm the defect and acceptance evidence         |
| 2     | [Implement](../stages/implement.md) | Fix the shared root cause with regression evidence |
| 3     | [Review](../stages/review.md)       | Review through the authorized delivery path        |
| 4     | [Complete](../stages/complete.md)   | Reconcile and verify the integrated result         |

## Output

Report the current stage, approval state, verification, and next transition or
blocker under the parent skill's output contract.

## Rules

- Create a formal remote Bug record only when human intent, existing tracking,
  or repository policy requires it.
- Never create a backlog record for a Bug. Without a tracking rule, leave remote
  state unchanged and continue local diagnosis.
- Complexity does not turn a Bug into a Feature.
- Keep any design notes or execution plan inside Triage, and add them only when
  risk warrants it. Never add Feature stages or a backlog record.
