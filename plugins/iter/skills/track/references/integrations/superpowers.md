# Superpowers Evidence Bridge

Superpowers owns its engineering methods, method selection, execution topology,
and review procedures. Track consumes their results and preserves the work
contract, required approvals, and tracking gates.

## Evidence mapping

| Missing work | Method owner when installed | Evidence Track records |
| ------------ | --------------------------- | ---------------------- |
| Problem, requirements, or material solution/design choices | `superpowers:brainstorming` | Settled outcome and decisions, proportional design artifact, required approval |
| Written multi-step execution plan | `superpowers:writing-plans` | Approved steps, boundaries, checks, and execution authority |
| Unexpected behavior or root-cause diagnosis | `superpowers:systematic-debugging` | Reproduction, diagnosed cause, and acceptance evidence; Bug notes remain in Triage |
| Implementation and checks | Owning context and its selected Superpowers methods | Complete scoped change, meaningful regression/acceptance evidence, reconciliation, required-check results |
| Code review or requested changes | `superpowers:requesting-code-review` / `superpowers:receiving-code-review` | Review findings and outcome, correction evidence, unresolved human or integration gate |
| Completion verification | `superpowers:verification-before-completion` | Evidence covering the actual integrated result and environment |

## Rules

- Consult only matching installed methods for the missing engineering work.
  This table is not an itinerary or a requirement to invoke every row.
- Required approvals, artifact depth, and delivery authority follow human and
  repository instructions. Reuse existing approvals and equivalent evidence.
- Track neither chooses plan executors nor duplicates review or verification
  procedures. The execution context supplies the evidence.
- Without Superpowers, hand the missing engineering work to the owning execution
  context and keep the unmet gate explicit. Tracking remains usable without
  installing dependencies or inventing an engineering fallback.
