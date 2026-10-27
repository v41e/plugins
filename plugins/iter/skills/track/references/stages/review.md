# Review

## Purpose

Track independent review, supported corrections, and the applicable human
decision for the selected workflow.

## Input

The original intent, accepted decisions, exact revision and whole proposed
scope, owning instructions, relevant local examples, and supplied check/review
evidence with its limits. Identify uncommitted changes alongside any commit
range. Implementation requires passing affected and required checks.

## Workflow

1. Obtain independent evidence from the execution owner covering the relevant
   stage. Each attempt uses a fresh task-scoped reviewer context. The owner
   selects reviewers under caller policy; multiple reviewers receive the same
   fixed revision with explicit scopes and distinct reports:

   | Stage | Judgment |
   | ----- | -------- |
   | Work contract (draft or Issue) | Outcome, scope, and important uncertainties at proportional depth |
   | Spec | Contracts, architecture, scope, accepted decisions, and simplicity |
   | Plan | Steps, dependencies, verification, and execution/delivery boundaries |
   | Implementation | Whole proposed change: behavior, contracts, docs, simplicity, reuse, tests, compatibility, generated output, and defects |
   | Published PR | Security, actual delivered scope, changes since prior review, and current checks/reviews for the exact remote head |

2. Record each reviewer's revision/scope, verdict, evidenced findings, and
   limits in the agreed evidence surface. Keep the author's validation and
   response separate. The execution owner resolves findings against intent and
   evidence; votes or averaged scores cannot dismiss a supported defect.
   Unsupported findings and optional nits do not force changes.
3. Track the next transition from the supplied evidence:

   - **Ready:** required checks and reviews cover the final revision, with
     supported blocking findings resolved; proceed to the applicable human
     checkpoint or already-authorized next stage.
   - **Corrections required:** the execution owner corrects supported findings,
     then obtains fresh affected independent review. Reuse unaffected evidence.
   - **Insufficient evidence:** return missing context or verification to its
     owner; hold dependent progress until the gap is resolved.

   Stop for stalled progress, an unresolved material decision or blocker, or the
   caller's unsuccessful-round limit. A successful round at that limit may
   advance. Present unresolved findings and the needed human decision.
4. Summarize the human decision, agent evidence, and remaining uncertainty with
   links to the exact reviewed artifact. Record applicable approval and reuse
   existing grants. Feature draft, spec, and plan approvals remain distinct;
   Bug/Task review does not add Feature gates.
5. Track delivery under the caller's contract. For a published PR, verify review
   and current checks against its actual head; corrections refresh affected
   evidence and materially affected approvals before integration.

## Output

Exact reviewed revision and scope, review evidence, author responses, unresolved
findings, human decision/authority, and delivery state.

## Rules

- Review execution and delivery belong to the owning context. Passing checks,
  self-review, and host tool-approval review do not replace independent
  judgment.
- Local examples establish context and compatibility, not an automatic quality
  standard. Narrow evidence covers only its actual judgment.
- Existing commits remain valid review inputs; do not uncommit resumed work to
  manufacture a working-tree diff.
- The delivery owner follows repository Git policy and configured signing.
  Record Git metadata, signing, permission, or approval blockers; retain the
  selected checkout and reviewed diff. Never bypass a denial or disable signing.
- PR types and green checks establish neither automatic merge eligibility nor
  merge or release authority.
