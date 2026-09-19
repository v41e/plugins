# Complete

## Input

Required reviews passed and the work reached the repository's authorized
integration boundary.

## Workflow

1. Read the implementation and review history.
2. Verify reconciliation and artifact cleanup were included in the reviewed
   result. Return missing changes through Implement and Review.
3. Verify that evidence covers the actual integrated result and environment.
   Rerun affected checks when either changed, evidence is incomplete, or policy
   requires it.
4. Verify linked formal records and tracked items are done. Correct them when
   authorized.
5. Report any release, publish, production, or promotion work that remains under
   human ownership.

## Output

Report completion with current evidence.

## Rules

- Do not merge, push a production branch, release, publish, or deploy merely
  because implementation is complete.
