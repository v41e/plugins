# Lifecycle Contracts

## Input

Work type, current contract and artifacts, human authorization, repository
policy, and evidence supplied by the owning execution context.

## Workflow

### Paths

| Work | Trigger | Tracking gates |
| ---- | ------- | -------------- |
| Feature | New or materially expanded capability | Ideate → Design → Plan → Implement → Review → Complete |
| Bug | Observed behavior contradicts an expectation | Triage → Implement → Review → Complete |
| Task | Maintenance, dependencies, configuration, documentation, refactoring, or operations that are neither Feature nor Bug | Scope → Implement → Review → Complete |

Resume the first unmet gate; existing evidence may already satisfy earlier
gates. Preserve each path's order without restarting completed methods. Return
to the earliest affected gate when new intent or repository state materially
changes the contract.

### Shared controls

- Keep one independently prioritizable outcome. Fold related questions,
  decisions, maintenance, and substeps into it; retire redundant records.
- Early exploration can remain in chat. Persist a draft, specification, or plan
  only at proportional depth in the expected owning repository; move or retire
  misplaced drafts. Unresolved ownership stays in chat or an appropriate
  cross-repository planning surface.
- Bounded, low-risk Design and Plan may stay inline when policy and human intent
  permit. Never require a record, specification, plan, branch, worktree, or
  delivery record merely to represent a gate. Temporary artifacts are not
  canonical documentation.
- Remote tracking requires an owning surface and applicable policy, human
  direction, or existing owned tracking. An explicit remote-tracking opt-out
  wins. Missing optional records do not block the work.
- Reuse settled authorization. Separate plan approval is required only when
  human intent or repository policy requires it. Material choices still owned
  by the human and required approvals remain explicit gates.
- Preserve the selected checkout, unrelated changes, and nearest Git policy.
  Handoffs carry only the authorized contract, approved decisions and steps,
  existing evidence, and remaining gate; they do not authorize task dispatch.

### Current gate

| Gate | Record and require before advancing |
| ---- | ----------------------------------- |
| Ideate | One refined Feature outcome and ownership when known. An ideation-only request ends here. Local drafts and mapped backlog records are optional; their absence or unresolved ownership does not block Design in chat or a cross-repository planning surface. Formal work records, specifications, plans, branches, and implementation belong to later gates. |
| Design | Settled problem, outcome, decisions, constraints, interfaces, verification, and non-goals at proportional depth; any required design approval. Create or promote a formal record only when a repository contract is required. Publish an approved specification when both it and a formal record exist. A design-only request ends here. |
| Plan | Settled owners, files, checks, boundaries, and implementation steps; execution authority and any required plan approval. Publish an approved local plan when a formal record exists; synchronize mapped ready state. A planning-only request ends here. |
| Triage | Expected and observed behavior, reliable reproduction and supporting evidence, priority, owner, diagnosis, and acceptance evidence. A human report remains untriaged until evidence confirms the defect; an agent-discovered failure may proceed with sufficient evidence. Missing defect or acceptance evidence blocks advancement. |
| Scope | Task problem, proposed solution, owner, and deterministic acceptance evidence; alternatives or context only when useful. A scoping-only request ends here; otherwise scope and execution authority must be understood and required approvals satisfied. |
| Implement | Understood authorized contract and required approvals; mapped active state and actual start when supported. Obtain the complete change's reconciliation of code, tests, canonical docs, and owning configuration, artifact cleanup, and passing affected and required checks from the execution context. Meaningful regression or acceptance evidence should cover changed behavior. Failures return to that context within scope. |
| Review | Relevant diff, generated output, compatibility boundary, and current verification; required local human review and separate delivery grants. Record authorized delivery and related formal records, summary, verification, and material notes. Distinguish local checks/review from remote checks/review. Requested changes return to Implement with delivery open, followed by renewed checks and review. |
| Complete | Required reviews passed and authorized integration reached; evidence covering the actual integrated result and environment; reconciliation and artifact cleanup included in the reviewed result. Missing changes return through Implement and Review; missing, stale, or policy-required verification goes to the execution context. Correct linked formal records and done state only when authorized. Report remaining release, publish, production, or promotion work under human ownership. |

### Delivery gates

A required local human review checkpoint precedes the first delivery mutation
unless explicitly approved or waived for this work. Access approval is separate
from review approval and delivery authority. Existing commits remain valid
review inputs; do not uncommit resumed work to manufacture a working-tree diff.

The owning execution context follows the permitted delivery path and configured
signing. Track records its state; it does not perform Git delivery or create a
delivery record. Review and authorized integration remain required before done.

Record Git metadata, signing, permission, or approval failures as delivery
blockers and retain the reviewed diff. The owning execution context uses
configured signing and approval mechanisms. Never bypass a denial or treat
access as delivery authority.

## Output

Current gate, supporting evidence, satisfied and outstanding approvals,
authorized tracking changes, delivery state, and next transition or handoff.

## Rules

- Complexity does not turn a Bug into a Feature. Never create a Bug backlog
  record; optional design notes and plans remain inside Triage when risk warrants
  them. Task work adds neither Feature ideation nor Bug reproduction.
- Never weaken a failed check or silently expand scope to pass a gate. Ask the
  execution context for the missing evidence; tracking state is not proof.
- Completion of implementation does not authorize merging, a production-branch
  push, release, publication, or deployment.
