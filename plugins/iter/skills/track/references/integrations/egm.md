# EGM Evidence Bridge

Load when the owning context selected EGM or supplied EGM artifacts need
reconciliation. EGM supplies exploration, design, and document-review methods;
Track consumes evidence under the caller's existing workflow and authority.

## Evidence Mapping

| When | Capability | Result |
| ---- | ---------- | ------ |
| The owner selected EGM to explore unsettled scope | `egm-brainstorm` | One concepts brief or existing work contract, considered alternatives, decisions, and unresolved questions |
| The owner selected EGM for feature design | `egm-draft` within the selected scope | One specification linked to the work contract, material decisions, and predecessor reconciliation |
| A feature spec needs the selected document review | `egm-review` with `Step: feature_spec`, or caller-selected review using EGM criteria | Independent findings and limits for the exact final spec revision and required dimensions |
| A standalone implementation plan needs the selected document review | `egm-review-loop` with `SemanticTarget: full file`, or caller-selected EGM readiness/codebase criteria | Plan actionability and source-reference evidence for the actual plan; no duplicate authoring |

## Composition

When EGM supplies design and [Superpowers](superpowers.md) supplies planning,
the caller explicitly excludes EGM's Detailed Implementation Plan authoring.
Retain finalization and predecessor reconciliation, then supply the spec to
`superpowers:writing-plans` without another brainstorm or spec. Follow the
[Feature workflow](../workflows/feature.md) for separate or combined design/plan
checkpoints.

The caller supplies the accepted predecessor file as `egm-draft`'s
`Context File` when available. Issue-only intake uses the accepted record
content for both intake and final predecessor reconciliation, even without a
predecessor file; skip unrelated local autodiscovery and do not create another
brief.

Use the caller's artifact owners. A concepts brief can be the one local draft;
an existing Issue still owns its contract. With a shared `docs/` layout, callers
can place EGM artifacts in `docs/egm/<work>/` and Superpowers plans in
`docs/superpowers/plans/`. Pass an `EGM artifact directory:` line with the
resolved directory and an explicit final spec path. Preserve existing locations
and link predecessors.

## Evidence Boundaries

Brainstorm reviewers inspect a hypothesis before brief synthesis; that alone
does not review the written brief. The top-level implementation preset expects a
detailed-section split; standalone plans use the full-file target above.
Document review does not cover implementation or published-PR judgment.

The [Review stage](../stages/review.md) governs evidence and correction gates.
Read installed EGM instructions for methods, personas, and standards.
