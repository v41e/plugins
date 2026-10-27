# Complete

## Purpose

Track completion against the actual authorized integrated result and
environment.

## Input

Required reviews passed and the authorized integration boundary was reached.

## Workflow

1. Confirm reconciliation and delivery exclusions were reviewed. Retire local
   artifacts only after their useful content and approved snapshots are safely
   represented in the owning docs, Issue, or PR. Retain actionable or unsynced
   drafts, specs, plans, and review evidence; a spec alone does not retire its
   draft. Report missing reconciliation to the execution context.
2. Require evidence covering the actual integrated result and environment. Hand
   missing, stale, or policy-required verification to the execution context.
3. Correct linked formal records and mapped done state only when authorized and
   the gate is satisfied.
4. Report remaining release, publish, production, or promotion work under human
   ownership.

## Output

Completion with current integrated-result evidence, or the unmet gate and
handoff.

## Rules

- Integration alone does not satisfy missing verification.
- Required review and authorized integration precede Done. Completion grants no
  authority to merge, push a production branch, release, publish, or deploy.
