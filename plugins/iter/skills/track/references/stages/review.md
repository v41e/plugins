# Review

## Purpose

Track supplied reviews, the human's delivery judgment, and authorized delivery
state.

## Input

The complete change with passing affected and required checks.

## Workflow

1. Record final supplied code-defect review, author correction evidence, and
   verification for the exact diff/revision, generated output, and compatibility
   boundary. Human delivery judgment covers
   behavior, general logic, API documentation, quality, and readiness; agent
   evidence covers detailed investigation and checks.
2. Require equivalent review evidence for major, security-sensitive, or
   compatibility-sensitive changes; require independent review when policy
   calls for it. Reuse review already supplied by the owning method.
3. Record evidence of any required local human checkpoint before the first
   delivery mutation; keep it unmet until approved or explicitly waived for this
   work. Preserve separate delivery grants and record authorized delivery
   evidence, related formal records, verification, and material notes.
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
