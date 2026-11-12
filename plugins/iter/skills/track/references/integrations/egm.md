# EGM Evidence Bridge

Load when the owning context selected EGM or supplied EGM artifacts need
reconciliation. Track consumes EGM evidence under the caller's existing workflow
and authority.

## Evidence Mapping

| When | Capability | Result |
| ---- | ---------- | ------ |
| The owner selected EGM to explore unsettled scope | `egm-brainstorm` | One concepts brief or existing work contract, considered alternatives, decisions, and unresolved questions |
| The owner selected EGM for feature design | `egm-draft` within the selected scope | One specification linked to the work contract, material decisions, and predecessor reconciliation |
| The owner selected EGM for design and planning | `egm-draft` through its Detailed Implementation Plan | One artifact containing the specification, detailed plan, and verification |
| A design-only artifact needs review | `egm-review` with `Step: feature_spec`, or caller-selected review using EGM criteria | Independent findings and limits for the exact final spec revision |
| A combined EGM design and plan needs review | `egm-review` with `Step: uninterrupted`, or the caller's selected review covering both | Design and implementation readiness evidence for the same revision |
| A standalone implementation plan needs the selected document review | `egm-review-loop` with `SemanticTarget: full file`, or caller-selected EGM readiness/codebase criteria | Plan actionability and source-reference evidence for the actual plan; no duplicate authoring |

## Composition

One EGM artifact can supply Design and Plan evidence. Record the section and
revision used for each stage. Use the
[Feature workflow](../workflows/feature.md) for separate or combined
checkpoints.

When EGM owns design only, omit its Detailed Implementation Plan and finalize
and reconcile the spec. Pass that spec to a separate planner when selected.

When Superpowers will execute a combined EGM artifact, use the
**Task Structure** from `superpowers:writing-plans` as a format reference for
`### Task N: …` blocks inside EGM's Detailed Implementation Plan. Keep
applicable constraints and verification inside each task for extraction. Give
the selected [Superpowers executor](superpowers.md) the accepted artifact as
`PLAN_FILE` and its design section as the spec.

The caller supplies the accepted predecessor file as `egm-draft`'s
`Context File` when available. Issue-only intake uses the accepted record
content for both intake and final predecessor reconciliation, even without a
predecessor file; skip unrelated local autodiscovery and do not create another
brief.

Use the caller's artifact owners. A concepts brief can be the local draft. With
a shared `docs/` layout, keep EGM artifacts, including combined designs and
plans, in `docs/egm/<work>/`. Standalone Superpowers plans can live under
`docs/superpowers/plans/`. Pass the resolved `EGM artifact directory:` and the
final artifact path. Preserve existing locations and link predecessors.

## Evidence Boundaries

Brainstorm reviewers inspect a hypothesis before brief synthesis; that alone
does not review the written brief. The top-level implementation preset expects a
detailed-section split; standalone plans use the full-file target above.
Document review does not cover implementation or published-PR judgment.

The [Review stage](../stages/review.md) governs evidence and correction gates.
Read installed EGM instructions for methods, personas, and standards.
