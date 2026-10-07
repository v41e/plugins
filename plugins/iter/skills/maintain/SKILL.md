---
name: maintain
description: Use when an owning project needs a bounded pass of authorized repairs or canonical documentation reconciliation.
---

# Maintain

## Purpose

Reconcile one owner's current state, advance real authorized maintenance, and
reassess after each outcome. Track records work state; the owning execution
context supplies engineering methods.

## Input

Owning context, maintenance scope, current signals and work contracts,
authorization, delivery permissions, and run budget or stopping conditions.

| Mode | Read when |
| ---- | --------- |
| [Engineering](references/modes/engineering.md) | Reliability, dependencies, configuration, or delivery needs repair |
| [Documentation](references/modes/documentation.md) | Owned knowledge needs reconciliation with current truth |

## Workflow

1. Establish the selected checkout, project instructions, contribution policy,
   contracts, and current ownership. Read the relevant mode.
2. Reconcile signals with current local and task evidence before choosing work.
   Read the [GitHub mappings](references/platforms/github.md) when needed.
   Resume this assignment's work; preserve another active owner's assignment.
3. Choose an evidenced correction inside the pass's authority. Compare impact,
   urgency, dependencies, and confidence. Keep additional opportunities as
   proposals when they require new scope or approval.
4. Use `iter:track` when repository policy requires it, the work is already
   tracked, materially undecided, or independently prioritizable. Reconcile the
   contract, approvals, gate, and evidence. Perform authorized work through the
   owning context's methods, mapped in [Superpowers](references/integrations/superpowers.md).
   Reconcile affected code, tests, docs, and owning configuration; complete
   required checks and independent final-revision review for substantive work,
   then follow the approved delivery scope. Return results to
   tracking. Track supplies no execution fallback.
5. Reassess remaining authorized work after each outcome. Continue independent
   eligible corrections while blocked work is held. Stop when scope is covered,
   the budget is reached, or adequate evidence shows no eligible work remains.

## Output

Confirmed changes and verification, delivery state, remaining scope or decisions,
and skipped, already-owned, blocked, or unexamined work. Distinguish a verified
no-op from insufficient evidence.

## Rules

- Stay in the owning context and selected checkout; preserve unrelated changes.
  Do not list saved projects, dispatch project-owned tasks, or edit other projects.
- Signals, drafts, status, silence, and access are not authorization. Reuse
  existing approvals and their covered execution, human review, commit, push,
  and PR scope. An approved plan naming PR delivery covers publication after
  checks/review without another discretionary pre-push checkpoint; human review
  occurs on the PR. Explicit local-only, publication holds, or required local
  human review win. Unapproved ideas remain proposals.
- Honor required review and delivery boundaries. Use configured signing and the
  approval mechanism for exact authorized Git operations; request only needed
  Git metadata access. A denial stops delivery; retain the diff and report the
  blocker. Never bypass it, broaden escalation, switch repositories, reconstruct
  Git metadata, substitute remote APIs, or disable signing.
- Missing or incomplete evidence is **Unknown** or **Partial**. Ending a run does
  not complete its work lifecycle; the next run resumes existing state.
- Never merge, release, deploy, create schedules, or modify live automations.
