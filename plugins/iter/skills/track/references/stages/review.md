# Review

## Purpose

Track supplied reviews, the human's delivery judgment, and authorized delivery
state.

## Input

The complete change with passing affected and required checks.

## Workflow

1. For substantive work, record independent review and passing affected/required
   checks covering the exact final revision, generated output, and compatibility
   boundary. Review original intent, accepted decisions, and relevant local
   examples; judge behavior, general logic, contracts, docs, simplicity, and
   readiness as well as defects. Passing tests alone do not prove alignment.
2. Record supported corrections, refreshed final-revision evidence, and the
   concise delivery summary using Track's handoff. Reuse equivalent supplied
   review; a narrower code-defect review covers only the judgment it performed.
3. Record the stated delivery authority. When an approved plan/execution scope
   covers focused PR delivery under repository policy, checks and review permit
   the owning context to commit, push, and publish that PR without another
   discretionary publication question or pre-push human checkpoint. Human review
   then occurs on the published PR. Explicit local-only, publication holds, or
   required local human review still bind; retain an unmet checkpoint until
   approved or explicitly waived. Record actual delivery evidence and material notes.
4. Distinguish local checks and review from remote checks and review. Requested
   changes return to Implement with delivery open, followed by renewed checks
   and review.

## Output

Review outcome, delivery state, and outstanding human or integration gate.
Advance to Complete only after required reviews and authorized integration.

## Rules

- Review methods and delivery belong to the owning execution context.
- Existing commits remain valid review inputs; do not uncommit resumed work to
  manufacture a working-tree diff.
- The delivery owner follows repository Git policy and configured signing.
  Record Git metadata, signing, permission, or approval blockers; retain the
  selected checkout and reviewed diff. Never bypass a denial or disable signing.
- Automatic merge eligibility is a separate policy decision; PR types and green
  checks alone establish neither eligibility nor merge authority.
