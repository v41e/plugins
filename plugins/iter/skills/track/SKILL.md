---
name: track
description: Use when repository work needs classification, resumption, approval and evidence tracking, or record synchronization.
---

# Track

## Purpose

Keep work contracts, approvals, evidence, and delivery state proportional and
resumable. Superpowers or the owning context supplies engineering methods.

## Input

Latest human intent, current repository state and instructions, work contracts,
approval evidence, local artifacts, and optional remote records.

## Workflow

1. Establish ownership, Git state, contribution policy, and existing records.
   Preserve the selected checkout and unrelated changes. Follow explicit links;
   use installed `locus:find` only when ownership or active work remains unclear.
2. Keep one independently prioritizable outcome. Compare current intent and
   repository evidence with tracked state; consolidate redundant records, reuse
   settled decisions and approvals, and update or retire stale artifacts. Return
   to the earliest affected gate after a material change.
3. Classify the work and read one workflow:

   - [Feature](references/workflows/feature.md): new or materially expanded capability.
   - [Bug](references/workflows/bug.md): observed behavior contradicts an expectation.
   - [Task](references/workflows/task.md): maintenance, dependencies, configuration,
     documentation, refactoring, or operations that are neither Feature nor Bug.

4. Follow that workflow's order and read only its first unmet stage. Existing
   evidence can satisfy earlier gates without restarting completed methods.
5. Record the contract, evidence, approval, and delivery state using existing
   surfaces. Read a platform adapter only when its synchronization applies:

   - [GitHub](references/platforms/github.md): mapped repository, Issue, Project,
     and existing pull-request records.

6. Hand missing engineering work to the owning execution context with the
   authorized contract, approved decisions and steps, existing evidence, and
   remaining gate. Read an integration only when installed and relevant:

   - [Superpowers](references/integrations/superpowers.md): engineering-method
     evidence supplied to tracking gates.

7. Synchronize authorized tracking changes and advance within requested scope
   only when evidence and approvals satisfy the gate. Report an unresolved
   material human decision, required approval, or blocked step as an unmet gate.

## Output

Work type, current gate or transition, changed records, evidence, approval and
delivery state, and smallest next action or execution handoff.

## Rules

- Track edits tracking records and artifact metadata. It does not implement,
  debug, review code, run engineering checks, commit, push, create pull requests,
  select executors, or dispatch tasks. A handoff does not authorize dispatch.
- Early exploration can stay in chat. Persist proportional drafts, specs, and
  plans in their expected owning repository; move or retire misplaced artifacts.
  Unresolved ownership stays in chat or a cross-repository planning surface.
  Bounded, low-risk Design and Plan may stay inline when policy and intent permit.
  A gate alone requires no record, artifact, branch, or worktree. Temporary
  artifacts are not canonical documentation.
- Remote tracking requires an owning surface and applicable policy, human
  direction, or existing owned tracking; explicit opt-out wins. Missing optional
  records or plugins require no setup and do not block work.
- Latest restrictions win. Access, drafts, status, and silence are not approval.
  Reuse settled authorization; preserve execution, review, commit, push, and
  delivery-record grants separately. Separate plan approval is required only by
  human intent or repository policy; unresolved material human choices and
  required approvals remain gates.
- A required local human review checkpoint precedes the first delivery mutation
  unless explicitly approved or waived for this work. Access approval is separate
  from review and delivery authority. Existing commits remain valid review inputs;
  do not uncommit resumed work to manufacture a working-tree diff.
- The delivery owner follows repository Git policy and configured signing. Track
  records delivery state and any Git metadata, signing, permission, or approval
  blocker; retain the reviewed diff. Never bypass a denial or treat access as
  delivery authority.
- Tracking state is not proof. Never weaken a failed check or expand scope to pass
  a gate; obtain missing evidence from the execution context. Required review and
  authorized integration precede Done; implementation completion does not
  authorize merge, production-branch push, release, publication, or deployment.
