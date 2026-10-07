# Superpowers Evidence Bridge

Superpowers owns engineering methods, method selection, execution topology,
and review procedures. Track consumes their results and preserves the work
contract, required approvals, and tracking gates.

## Evidence mapping

| When | Capability | Result |
| ---- | ---------- | ------ |
| Outcome, requirements, or material design choices are unsettled | `superpowers:brainstorming` | Refined outcome, settled decisions, remaining questions, and required human approval |
| Work needs a written multi-step plan | `superpowers:writing-plans` | Steps, dependencies, PR boundaries, checks, and stated execution/delivery scope for plan approval |
| A defect or unexpected failure needs diagnosis | `superpowers:systematic-debugging` | Reproduction, root cause, and acceptance evidence before proposing a fix |
| Changed behavior supports an executable regression or acceptance check | `superpowers:test-driven-development` | Meaningful failing and passing checks under repository verification policy |
| Independent work warrants parallel execution | `superpowers:dispatching-parallel-agents` | Owner-supplied results, resolved conflicts, and affected and required checks |
| An approved plan needs execution | `superpowers:subagent-driven-development` / `superpowers:executing-plans` | Owner-selected execution, complete scoped change, reconciliation, and verification |
| A substantive or policy-required change lacks equivalent code review | `superpowers:requesting-code-review` | Code-defect evidence toward the broader implementation review; spec/plan judgment remains distinct |
| Supplied code review requests changes | `superpowers:receiving-code-review` | Verified feedback, correction evidence, and remaining review or integration gate |
| An integration or branch-delivery decision remains unsettled | `superpowers:finishing-a-development-branch` | Required decision and authorized delivery evidence; reuse covered PR authority, while method completion grants none |
| Completion evidence is missing, stale, or does not cover the integrated result | `superpowers:verification-before-completion` | Verification of the actual integrated result and environment |

Design and planning jobs also apply within Bug Triage and Task Scope; they do not
add Feature stages. Follow Track's substantive review/summary/spec-then-plan
checkpoints. The owning context obtains suitable independent artifact review and
any judgment absent from narrower method evidence; a code-defect review is not
spec/plan review. Reuse supplied approvals and equivalent final-revision evidence.

Track records results and hands missing engineering work back to the execution
context, including when Superpowers is unavailable. It neither selects executors
nor runs these methods or their review procedures.
