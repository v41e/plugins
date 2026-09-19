# Implement

## Input

The work contract is understood, execution is authorized, and any approvals
required by the workflow or repository policy are satisfied.

## Workflow

1. Apply the mapped active status to tracked work and record the actual start
   when the selected platform supports it.
2. Continue in the selected checkout or worktree and follow the nearest Git
   policy.
3. Choose direct, plan-execution, or parallel topology based on coupling.
4. Implement the complete requested change, using a failing check for changed
   behavior when it provides meaningful regression or acceptance evidence.
5. Reconcile code, tests, canonical docs, and owning configuration; retire stale
   temporary artifacts before Review.
6. Integrate once in the main agent, inspect the result, and run affected and
   repository-required checks. Fix task-caused failures within scope.

## Output

Proceed to Review only with passing evidence.

## Rules

- If a check fails, diagnose it; never weaken the check or silently expand scope.
