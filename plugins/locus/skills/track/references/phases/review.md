# Review

## Input

The integrated implementation passes its affected checks.

## Workflow

1. Review the contract, diff, generated output, compatibility boundary, and
   fresh evidence.
2. Satisfy any required local human review checkpoint before the first delivery
   mutation: present the verified uncommitted diff and material decisions, then
   wait unless that checkpoint was already approved or explicitly waived for the
   task. Access approval is not review approval or delivery authority. Preserve
   commit, push, and delivery record grants separately; newer restrictions
   override them.
3. Follow the delivery path set by repository policy and human direction in the
   selected checkout or worktree. Use configured commit signing. If permitted,
   commit, push, and create or update the delivery record in that order; or
   present the direct change. Never invent a delivery record.
4. In a delivery record, include related formal records, summary, verification,
   and material notes.
5. Apply the mapped review status when tracked work exposes one.
6. Report local checks and review separately from remote checks and review; each
   claim covers only the evidence actually observed.
7. Verify requested changes, return to Implement, and keep the delivery record
   open. Then repeat deterministic checks and Review.

## Output

Report review status and any outstanding review or integration gate.

## Rules

- Wait for required review and integration. Integrate only when the nearest
  authority assigns that responsibility.
- If Git metadata access or signing fails, stay in the selected worktree and
  request access only for the resolved Git common directory and current worktree
  administration directory. If access is unavailable or denied, keep the
  reviewed diff and report the blocker. Do not switch repositories, reconstruct
  Git metadata, use remote APIs as a substitute, disable signing, or bypass a
  denial.
