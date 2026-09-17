---
name: operate
description: Use when authorized engineering or canonical documentation needs one bounded run in its owning project context.
---

# Operate One Authorized Run

Make useful, verified progress toward the caller's goal. Operate manages the
execution pass; the applicable work lifecycle governs each change.

## Input

Intended outcome, owning context, authorized scope, delivery permissions, and
budget or stopping conditions for this manual or scheduled run.

| Mode            | Purpose                                  | Reference                                             |
| --------------- | ---------------------------------------- | ----------------------------------------------------- |
| `engineering`   | Advance capabilities and reliability     | [engineering.md](references/modes/engineering.md)     |
| `documentation` | Keep owned knowledge accurate and useful | [documentation.md](references/modes/documentation.md) |

## Workflow

1. Read the selected mode, project instructions, contribution policy, and work
   contracts. Establish the Git root, working state, and ownership.
2. Gather relevant evidence using the [GitHub adapter](references/platforms/github.md)
   and its selected-mode references when applicable. Use the
   [Superpowers integration](references/integrations/superpowers.md) for artifacts
   and engineering methods.
3. Identify worthwhile work within scope, reconciling source, prior decisions,
   tasks, PRs, and newer results. Resume this assignment's work; do not duplicate
   another active owner's work.
4. Execute through one applicable workflow:
   - When Locus Track is installed and tracking applies, use it to classify new
     work or resume the current stage. It governs implementation, review, and
     delivery; do not repeat those steps through Operate.
   - Otherwise follow repository policy: establish the cause or acceptance
     criteria, make the smallest complete change, verify changed behavior and
     required checks, then follow the authorized review and delivery path.
5. Reassess after each outcome. Continue independent authorized work; hold blocked
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
