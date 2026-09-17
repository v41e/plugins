# Engineering Mode

## Input

An authorized change or maintenance scope, its intended outcome, and relevant
code, tests, Issues, plans, PRs, tasks, and workflow results.

## Workflow

1. For a concrete assignment, establish the acceptance criteria or reproduced
   defect. For maintenance, investigate where reliability, delivery, or usability
   would benefit most; use failures and backlog as evidence, not the entire agenda.
2. Compare candidates by impact, urgency, dependencies, and confidence. Trace
   defects to their shared cause and distinguish necessary fixes from new scope.
3. Carry selected work through the parent skill's execution workflow. Use focused
   regression or acceptance checks and repository-required verification.
4. Reconcile results before continuing the pass. A superseded failure or one
   blocked candidate does not exhaust independent authorized work.

## Output

Explain what capability or reliability improved and the evidence supporting it.
Identify remaining risks, delivery or review needs, and worthwhile follow-ups.

## Rules

- Supersede a workflow failure only with a newer success for the same workflow,
  branch, and commit.
- Keep changes independently reviewable. Investigation may reveal opportunities;
  implementing them still requires authority within the pass.
