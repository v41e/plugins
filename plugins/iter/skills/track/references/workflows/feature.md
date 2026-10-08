# Feature Workflow

## Purpose

Track a new or materially expanded capability from outcome through completion.

## Input

A new or materially expanded capability and its existing contract and evidence.

## Workflow

Resume the first unmet stage and identify each repeated Review by artifact kind,
exact revision, and required human decision. Reuse unchanged approvals and
equivalent evidence; an approved artifact authorizes only the next agreed phase.

| Order | Stage | Required outcome |
| ----- | ----- | ---------------- |
| 1 | [Ideate](../stages/ideate.md) | Concise draft outcome, scope, and ownership when known |
| 2 | [Review](../stages/review.md) (draft) | Quick independent draft review, short summary, and human draft approval permitting Design |
| 3 | [Design](../stages/design.md) | Identified specification and material decisions |
| 4 | [Review](../stages/review.md) (spec) | Independent final-spec review/corrections, concise summary, and human spec approval permitting Plan |
| 5 | [Plan](../stages/plan.md) | Identified implementation steps and proposed execution/delivery scope |
| 6 | [Review](../stages/review.md) (plan) | Independent final-plan review/corrections, concise summary, and human plan/execution approval covering the agreed delivery route |
| 7 | [Implement](../stages/implement.md) | Complete authorized change and passing required checks |
| 8 | [Review](../stages/review.md) (change/PR) | Independent final-change review/checks before covered publication; concise summary, human PR review, and authorized integration |
| 9 | [Complete](../stages/complete.md) | Verified authorized integrated result |

Corrections to a draft, spec, plan, or implementation return to Ideate, Design,
Plan, or Implement respectively, followed by its Review checkpoint with current
evidence. Reopen materially affected approvals only. Missing integrated-result
verification remains at Complete; changes to the implementation require renewed
Implement and Review evidence.

## Output

Current gate, evidence, approval state, and next transition or execution handoff.

## Rules

- Ideation-only, design-only, and planning-only requests end with the requested
  artifact and its applicable Review checkpoint; approval does not expand the request.
- Draft approval permits design; spec approval permits planning. Neither grants
  implementation or publication authority. Plan/execution approval covers only
  its stated, authorized scope; explicit holds and local-only instructions win.
