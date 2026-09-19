---
name: operate
description: Use when authorized engineering or canonical documentation needs one bounded run in its owning project context.
---

# Operate One Authorized Run

Carry the authorized outcome through implementation, inspection, and appropriate
verification within the run's limits. The applicable work lifecycle governs each
change; Operate owns continuation and stopping.

## Input

Intended outcome, owning context, authorized scope, delivery permissions, and
budget or stopping conditions for this manual or scheduled run.

| Mode            | Purpose                                  | Reference                                             |
| --------------- | ---------------------------------------- | ----------------------------------------------------- |
| `engineering`   | Advance capabilities and reliability     | [engineering.md](references/modes/engineering.md)     |
| `documentation` | Keep owned knowledge accurate and useful | [documentation.md](references/modes/documentation.md) |

## Workflow

1. Read the selected mode, project instructions, contribution policy, and work
   contracts. Establish the Git root, working state, and execution ownership.
2. Gather current relevant read-only local and remote evidence before selecting
   work. When GitHub is needed, read the [GitHub adapter](references/platforms/github.md)
   and its selected-mode references. Reconcile source, prior decisions, tasks,
   PRs, and newer results; resume this assignment's work and do not duplicate
   another active owner's work.
3. Resolve the lifecycle owner before selecting execution integrations:
   - When installed Locus Track applies, read Track. It classifies new work or
     resumes its current stage, selects the stage methods, and owns
     implementation, review, and delivery. Operate retains run scope,
     reassessment, continuation, and stopping.
   - Otherwise, Iter owns this run's execution workflow.
4. In Iter's independent fallback, read the
   [Superpowers integration](references/integrations/superpowers.md) only for
   matching artifacts or engineering methods.
5. In Iter's independent fallback, follow repository policy: establish the
   cause or acceptance criteria, make the smallest complete change, inspect the
   result, and complete affected and required checks. Fix task-caused failures
   within scope, then follow the authorized review and delivery path.
6. Reassess after each outcome. Continue independent authorized work; hold blocked
   or unapproved work. Stop when scope is covered, the budget is reached, or no
   eligible work remains.

## Output

Explain progress, verification, delivery state, and remaining scope or decisions,
including skipped, already-owned, blocked, or unexamined work. A verified no-op
requires adequate evidence. Keep opportunities outside authority as proposals.

## Rules

- Stay in the authorized owning context and selected checkout; preserve unrelated
  changes. Do not list saved projects, dispatch tasks, or edit other projects.
- Approval requires explicit evidence; drafts, status, silence, and access grants
  do not authorize work. Preserve commit, push, and PR grants separately; the
  latest human restriction wins.
- Honor required human review before delivery. Use configured signing and the
  approval mechanism for exact authorized Git operations; request only the
  necessary Git metadata access. A denial stops delivery. Never bypass it,
  broaden escalation, switch repositories, reconstruct Git metadata, substitute
  remote APIs, or disable signing. Retain the diff and report the blocker.
- Missing or incomplete evidence is **Unknown** or **Partial**, not success.
- A new run resumes existing work; it does not restart its lifecycle. Ending a
  run does not establish that the work is complete.
- Never merge, release, deploy, create schedules, or modify live automations.
