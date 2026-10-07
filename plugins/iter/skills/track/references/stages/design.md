# Design

## Purpose

Track a settled Feature design and its review and approval state.

## Input

A refined Feature outcome needing a settled design.

## Workflow

1. Require the settled problem, outcome, decisions, constraints, interfaces,
   verification, and non-goals at proportional depth.
2. For substantive work, record independent review of the exact specification
   against original intent, accepted decisions, and relevant local examples.
   Validate and resolve supported findings, refresh final-revision evidence, then
   present the concise summary for explicit human spec approval. Follow Track's
   review handoff; keep unresolved material choices explicit. Human judgment
   covers contracts, architecture, scope, and simplicity.
3. Once settled and required approvals are satisfied, create or promote a formal
   work record only when a repository contract is required. When it and an
   approved local specification both exist, publish the specification using the
   selected platform's snapshot mapping.

## Output

Settled design, evidence, and approval state. A design-only request ends here;
otherwise advance to Plan when the gate is satisfied. Spec approval authorizes
planning, not implementation.

## Rules

- Missing design work returns to the owning context; Track records its result.
  Spec review judges the proposed contract and design; code-defect review does
  not substitute for that judgment.
