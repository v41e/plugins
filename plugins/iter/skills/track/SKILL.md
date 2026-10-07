---
name: track
description: Use when repository work needs classification, resumption, approval and evidence tracking, or record synchronization.
---

# Track

## Purpose

Keep work contracts, approvals, evidence, and delivery state proportional and
resumable.

## Input

Latest human intent, current repository state and instructions, work contracts,
approval evidence, local artifacts, and optional remote records.

## Workflow

1. Establish ownership, Git state, contribution policy, and existing records.
   Preserve the selected checkout and unrelated changes. Follow explicit links;
   use installed `locus:find` only when ownership or active work remains unclear.
2. Compare current intent and repository evidence with tracked state. Make
   material changes since approval visible and return to the earliest affected
   gate; reuse unaffected decisions and approvals. Retire stale artifacts,
   consolidate redundant records, and split independently prioritizable
   outcomes before implementation when useful. Retain human-reserved comparison
   evidence until its purpose is complete and removal is authorized; an `-old`
   suffix alone does not make it stale. Interpret mixed feedback per outcome:
   authorized corrections may proceed; exploration and deferred ideas stay proposals.
3. Classify the work and read one workflow:

   - [Feature](references/workflows/feature.md): new or materially expanded capability.
   - [Bug](references/workflows/bug.md): observed behavior contradicts an expectation.
   - [Task](references/workflows/task.md): maintenance, dependencies, configuration,
     documentation, refactoring, or operations that are neither Feature nor Bug.

4. Resume the first unmet stage in workflow order using its linked contract.
   Existing evidence can satisfy earlier gates without restarting completed
   methods. For substantive Design, Plan, or Review, record the owning context's
   handoff: exact artifact/revision and original intent, accepted decisions, and
   relevant local examples → suitable independent review → validated corrections
   and final-revision evidence → concise summary → required human decision.
   The execution context obtains `artifact_reviewer` when available or equivalent
   read-only review; Track does not select reviewers. Artifact review is distinct
   from host tool-approval review. Reuse equivalent evidence for the same revision
   and scope; refresh affected evidence after corrections. Solicit approval only
   after review and supported corrections cover the final artifact, including
   interactive questions. At material decision or review checkpoints, identify
   **Human decision**, **Agent evidence**, and **Remaining uncertainty** in the
   existing artifact or response. Briefly name its reviewed identity, contracts,
   risks, consequential assumptions, intentional differences, findings, and
   evidence limits; link details. Summary approval covers its exact artifact;
   full spec/plan reading is not an additional gate. Omit framing for trivial work.
5. Record the contract, evidence, approval, and delivery state using existing
   surfaces. For remote synchronization, use the relevant platform mapping:

   - [GitHub](references/platforms/github.md): mapped repository, Issue, Project,
     and existing pull-request records.

6. Hand missing engineering work to the owning execution context with the
   authorized contract, approved decisions and steps, existing evidence, and
   remaining gate. The execution owner investigates options and established
   native/library/local patterns, chooses and discloses routine defaults, and
   presents unsettled material choices for human decision. Continue independent
   authorized preparation while dependent work waits. For supplied method
   evidence, use the installed integration:

   - [Superpowers](references/integrations/superpowers.md): engineering-method
     evidence supplied to tracking gates.

7. Synchronize authorized tracking changes and advance within requested scope
   only when evidence and approvals satisfy the gate. Report an unresolved
   material human decision, required approval, or blocked step as an unmet gate.

## Output

Work type, current gate or transition, changed records, final evidence, remaining
uncertainty, human decisions, approval and delivery state, and smallest next action
or execution handoff. Keep specs, plans, and PRs concise, with short pointers to
the interfaces or passages needing human judgment.

## Rules

- Track edits tracking records and artifact metadata. It does not implement,
  debug, review code, run engineering checks, commit, push, create pull requests,
  select executors, or dispatch tasks. A handoff does not authorize dispatch.
- Keep early exploration in chat and proportional artifacts in their owning
  repository; move or retire misplaced artifacts. Unresolved ownership stays in
  chat or a cross-repository planning surface. Bounded, low-risk Design and Plan
  may stay inline when policy and intent permit; a gate alone requires no artifact,
  record, branch, or worktree. Temporary artifacts are not canonical docs.
- Remote tracking requires an owning surface and applicable policy, human
  direction, or existing owned tracking; explicit opt-out wins. Missing optional
  records or plugins require no setup and do not block work.
- Latest restrictions win. Access, drafts, status, and silence are not approval.
  Reuse settled authorization; preserve execution, review, commit, push, and
  delivery-record scope, including grants covered by an approved delivery route.
- Substantive work has material product, architecture, contract, ownership,
  security, or scope choices, or a nontrivial implementation needing settled
  design and steps. Require separate spec then plan/execution approvals, including
  within Task Scope and Bug Triage. Routine low-risk work with a settled solution
  stays direct unless human or repository policy requires gates. Reversibility
  alone does not make a material choice routine. Explicit directions and stricter
  applicable policy win; reopen only materially affected approvals.
- Tracking state is not proof. Obtain missing or stale evidence from the
  execution context; never weaken a failed check or expand scope to pass a gate.
