# Review

## Purpose

Track supplied independent artifact review, its concise summary, and the human
decision specified by the selected workflow.

## Input

A handoff in existing artifacts or a concise brief containing:

- Artifact kind/phase, required human decision, and applicable authority.
- Original intent, accepted decisions, and exact revision, including relevant
  uncommitted changes.
- Owning instructions and quality standards, affected boundaries, and relevant
  local examples.
- Supplied review, correction, and check evidence with its revision, scope,
  environment, outcome, and limits. Implementation needs passing affected and
  required checks.

## Workflow

1. Require supplied independent review against the handoff. The execution owner
   obtains the first independent subagent review with fresh task-scoped context,
   using a suitable available profile when supplied. Keep draft review quick:
   outcome, scope, and important uncertainties, without demanding a design or
   plan. Specification review covers contracts, architecture, scope, and
   simplicity; plan review covers steps, dependencies, and delivery boundaries;
   implementation review covers behavior, logic, contracts, docs, simplicity,
   established capability reuse, readability, meaningful tests, readiness,
   generated output, compatibility, and defects.
2. Record validated findings, supported corrections, and final-revision
   evidence. Reuse equivalent review for the same revision and scope; retain
   unaffected evidence and refresh affected review after corrections, reusing
   the reviewer when available.
   Add reviewers only for distinct material risks or missing independent
   judgment. Narrow evidence covers only its actual judgment; missing or stale
   review remains an unmet requirement.
3. Summarize **Human decision**, **Agent evidence**, and **Remaining uncertainty**:
   reviewed identity, contracts, risks, consequential assumptions, intentional
   differences, findings, and evidence limits; link details. Idea summaries need
   only a few sentences. Solicit approval, including interactive questions, only
   after independent review and supported corrections cover the final artifact.
   Record the exact approved artifact and covered authority; summary approval
   does not require a separate full-artifact reading gate.
4. For implementation delivery, require passing checks and final independent
   review before covered commit/push/PR publication by the owning context. No
   discretionary pre-push checkpoint is needed for authorized PR delivery;
   record actual publication and the subsequent human PR decision separately.
   The implementation human checkpoint follows the covered delivery route,
   normally the published PR; explicit local-only, publication holds, or
   required local human review still bind. Distinguish local evidence from
   remote checks and reviews for the exact PR head.

## Output

Artifact kind and revision, supplied review/correction evidence, concise
summary, human decision and authority, delivery state where applicable, and
unmet requirements.

## Rules

- Review methods and delivery belong to the owning execution context.
- Local examples establish context and compatibility, not an automatic quality
  standard.
- Passing checks alone do not prove intent or architecture alignment. Artifact
  review is distinct from host tool-approval review.
- Existing commits remain valid review inputs; do not uncommit resumed work to
  manufacture a working-tree diff.
- The delivery owner follows repository Git policy and configured signing.
  Record Git metadata, signing, permission, or approval blockers; retain the
  selected checkout and reviewed diff. Never bypass a denial or disable signing.
- Automatic merge eligibility is a separate policy decision; PR types and green
  checks alone establish neither eligibility nor merge authority.
