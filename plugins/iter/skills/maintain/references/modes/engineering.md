# Engineering Maintenance

## Input

Authorized repair scope, intended result, current source and checks, and relevant
Issues, PRs, tasks, workflow results, or approved plans.

## Workflow

Establish the defect or acceptance evidence before correction. Trace a defect to
its shared cause; compare repair candidates by impact, urgency, dependencies,
and confidence. Use the owning context's methods for the smallest complete
change and meaningful regression or acceptance checks. Reconcile the result
before selecting another correction.

## Output

Improved reliability or maintainability, supporting evidence, and remaining
review, delivery, or scope needs.

## Rules

- A newer success supersedes a CI failure only for the same stable workflow ID,
  branch, and commit.
- Investigation can reveal new opportunities; it does not authorize their
  implementation. Keep corrections independently reviewable.
