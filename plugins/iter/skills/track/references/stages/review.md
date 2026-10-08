# Review

## Purpose

Track supplied independent artifact review, its concise summary, and the human
decision specified by the selected workflow.

## Input

Artifact kind and required human decision from the workflow; exact artifact or
change revision, original intent, accepted decisions, relevant local examples,
supplied review/correction evidence, and applicable authority. Implementation
artifacts also need passing affected and required checks.

## Workflow

1. Require independent supplied review suited to the artifact and its original
   intent, accepted decisions, and local examples. Draft review is quick: check
   the intended outcome, scope, and important uncertainties without demanding a
   detailed design or plan. Specification review covers contracts, architecture,
   scope, and simplicity; plan review covers steps, dependencies, and delivery
   boundaries; implementation review covers behavior, logic, contracts, docs,
   simplicity, readiness, generated output, and compatibility as well as defects.
2. Record validated findings, supported corrections, and final-revision evidence.
   Reuse equivalent supplied review; narrower evidence covers only the judgment
   it performed. Missing review or stale evidence remains an unmet requirement.
3. Record the concise summary using Track's handoff. Draft, specification, and
   plan approvals follow review and supported corrections of the final artifact.
   Keep an idea summary to a few sentences; other summaries remain proportional.
   Record the exact approved artifact and covered authority.
4. For implementation delivery, require passing checks and final independent
   review before covered commit/push/PR publication by the owning context. No
   discretionary pre-push checkpoint is needed for authorized PR delivery;
   record actual publication and the subsequent human PR decision separately.
   The implementation human checkpoint follows the covered delivery route,
   normally the published PR; explicit local-only, publication holds, or required
   local human review still bind. Distinguish local evidence from remote checks
   and reviews for the exact PR head.

## Output

Artifact kind and revision, supplied review/correction evidence, concise summary,
human decision and authority, delivery state where applicable, and unmet requirements.

## Rules

- Review methods and delivery belong to the owning execution context.
- Passing checks alone do not prove intent or architecture alignment. Artifact
  review is distinct from host tool-approval review.
- Existing commits remain valid review inputs; do not uncommit resumed work to
  manufacture a working-tree diff.
- The delivery owner follows repository Git policy and configured signing.
  Record Git metadata, signing, permission, or approval blockers; retain the
  selected checkout and reviewed diff. Never bypass a denial or disable signing.
- Automatic merge eligibility is a separate policy decision; PR types and green
  checks alone establish neither eligibility nor merge authority.
