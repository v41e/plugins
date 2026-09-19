# Feature Workflow

## Input

Use for a new or materially expanded capability.

## Workflow

Resume the first incomplete stage; read its contract before continuing.

| Order | Stage                               | Purpose                                            |
| ----- | ----------------------------------- | -------------------------------------------------- |
| 1     | [Ideate](../stages/ideate.md)       | Refine one outcome; persist it only when resumable |
| 2     | [Design](../stages/design.md)       | Settle the design at proportional depth            |
| 3     | [Plan](../stages/plan.md)           | Define authorized implementation steps             |
| 4     | [Implement](../stages/implement.md) | Deliver the complete authorized change             |
| 5     | [Review](../stages/review.md)       | Review through the authorized delivery path        |
| 6     | [Complete](../stages/complete.md)   | Reconcile and verify the integrated result         |

## Output

Report the current stage, approval state, verification, and next transition or
blocker under the parent skill's output contract.

## Rules

- Complete stages in order; resume the first incomplete stage.
- Preserve approval gates required by human intent or repository policy; reuse
  settled decisions and authorization. Separate artifacts are proportional.
- Record Design and Plan inline for bounded, low-risk work when policy and human
  intent permit it.
- Do not create a formal remote record, specification, plan, branch, worktree,
  or delivery record only to represent a stage.
- Use remote tracking only when an owning surface exists.
