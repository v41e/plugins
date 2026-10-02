# Superpowers Evidence Bridge

Superpowers owns engineering methods, method selection, execution topology,
and review procedures. Track consumes their results and preserves the work
contract, required approvals, and tracking gates.

## Evidence mapping

| Stage | Missing work | Method owner when installed | Evidence Track records |
| ----- | ------------ | --------------------------- | ---------------------- |
| Ideate | Problem, requirements, or outcome refinement | `superpowers:brainstorming` | One refined outcome and remaining questions |
| Design | Material design choices | `superpowers:brainstorming` | Settled design, proportional artifact, required approval |
| Plan | Written multi-step execution plan | `superpowers:writing-plans` | Settled steps, boundaries, checks, execution authority, any required plan approval |
| Triage | Reproduction or root-cause diagnosis | `superpowers:systematic-debugging` | Confirmed defect, diagnosed cause, acceptance evidence |
| Triage | Material fix choices or risky execution steps | `superpowers:brainstorming` / `superpowers:writing-plans` | Proportional decisions or plan retained in Triage; no Feature stages |
| Scope | Material solution choices or complex execution steps | `superpowers:brainstorming` / `superpowers:writing-plans` | Proportional contract and acceptance evidence retained in Scope |
| Implement | Changed behavior checks or unexpected failures | `superpowers:test-driven-development` / `superpowers:systematic-debugging` | Meaningful regression or acceptance evidence; failures remain unresolved until diagnosed and corrected |
| Implement | Implementation and execution topology | Owning context selects applicable methods, including `superpowers:dispatching-parallel-agents`, `superpowers:subagent-driven-development`, or `superpowers:executing-plans` | Complete scoped change, reconciliation, passing affected and required checks |
| Review | Code review or requested changes | `superpowers:requesting-code-review` / `superpowers:receiving-code-review` | Required review findings and outcome, correction evidence, remaining human or integration gate |
| Review | Integration decision or branch delivery | `superpowers:finishing-a-development-branch` | Human decision and authorized delivery evidence; method completion grants no integration authority |
| Complete | Missing or stale completion verification | `superpowers:verification-before-completion` | Evidence covering the actual integrated result and environment |

## Rules

- Consult only matching installed methods for missing engineering work. This
  table is not an itinerary or a requirement to invoke every row.
- Required approvals, artifact depth, and delivery authority follow human and
  repository instructions. Reuse existing approvals and equivalent evidence.
- Track neither chooses executors nor duplicates review or verification
  procedures. The execution context supplies the evidence.
- Without Superpowers, hand missing engineering work to the owning execution
  context and keep the unmet gate explicit; do not invent an engineering fallback.
