# Implement

## Purpose

Track supplied implementation progress and verification against the authorized
contract.

## Input

An understood authorized contract with required approvals satisfied.

## Workflow

1. Synchronize mapped active state and actual start when supported and
   implementation actually begins.
2. Record the supplied change and revision in the selected checkout, preserving
   unrelated work. Branches, worktrees, and commits follow the caller's
   contract; local commits do not establish publication authority.
3. Obtain reconciliation of code, tests, canonical docs, and owning
   configuration, plus passing affected and required checks. Keep temporary
   artifacts out of delivery by default; retain actionable local evidence until
   Complete confirms its safe retirement.
4. Record meaningful regression or acceptance evidence for changed behavior.
   Return failures to the execution context within scope.

## Output

Complete scoped change and passing evidence, or the missing evidence and
handoff.

## Rules

- Track records implementation evidence; it does not implement or run checks.
