# Shared Lifecycle Controls

## Input

Work type, current contract and artifacts, human authorization, repository
policy, and evidence supplied by the owning execution context.

## Workflow

- Follow the selected workflow's order and resume its first unmet gate. Existing
  evidence may satisfy earlier gates without restarting completed methods.
  Return to the earliest affected gate after a material contract change.
- Keep one independently prioritizable outcome. Fold related questions,
  decisions, maintenance, and substeps into it; retire redundant records.
- Early exploration can remain in chat. Persist a draft, specification, or plan
  only at proportional depth in the expected owning repository; move or retire
  misplaced drafts. Unresolved ownership stays in chat or an appropriate
  cross-repository planning surface.
- Bounded, low-risk Design and Plan may stay inline when policy and human intent
  permit. Never require a record, specification, plan, branch, worktree, or
  delivery record merely to represent a gate. Temporary artifacts are not
  canonical documentation.
- Remote tracking requires an owning surface and applicable policy, human
  direction, or existing owned tracking. An explicit remote-tracking opt-out
  wins. Missing optional records do not block the work.
- Reuse settled authorization. Separate plan approval is required only when
  human intent or repository policy requires it. Material choices still owned
  by the human and required approvals remain explicit gates.
- Preserve the selected checkout, unrelated changes, and nearest Git policy.
  Handoffs carry only the authorized contract, approved decisions and steps,
  existing evidence, and remaining gate; they do not authorize task dispatch.

### Delivery gates

A required local human review checkpoint precedes the first delivery mutation
unless explicitly approved or waived for this work. Access approval is separate
from review approval and delivery authority. Existing commits remain valid
review inputs; do not uncommit resumed work to manufacture a working-tree diff.

The owning execution context follows the permitted delivery path and configured
signing. Track records its state; it does not perform Git delivery or create a
delivery record. Review and authorized integration remain required before done.

Record Git metadata, signing, permission, or approval failures as delivery
blockers and retain the reviewed diff. The owning execution context uses
configured signing and approval mechanisms. Never bypass a denial or treat
access as delivery authority.

## Output

Current gate, supporting evidence, satisfied and outstanding approvals,
authorized tracking changes, delivery state, and next transition or handoff.

## Rules

- Never weaken a failed check or silently expand scope to pass a gate. Ask the
  execution context for the missing evidence; tracking state is not proof.
- Completion of implementation does not authorize merging, a production-branch
  push, release, publication, or deployment.
