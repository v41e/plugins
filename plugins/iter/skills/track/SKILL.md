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

For caller-supplied native Goal or scheduled-wakeup context, read the
[Codex mapping](references/harnesses/codex.md) when applicable.

## Workflow

1. Establish ownership, Git state, contribution policy, and existing records.
   Preserve the selected checkout and unrelated changes. Follow explicit links;
   use installed `locus:find` only when ownership or active work remains
   unclear.
2. Reconcile intent and repository evidence with tracked state. Expose material
   changes since approval and return to the earliest affected gate; reuse
   unaffected approvals. Retire stale artifacts, consolidate duplicate records,
   and split independently prioritizable outcomes before implementation when
   useful. Interpret mixed feedback per outcome:
   authorized corrections may proceed; exploration and deferred ideas remain
   proposals.
3. Classify the work and read one workflow:

   - [Feature](references/workflows/feature.md): new or materially expanded
     capability.
   - [Bug](references/workflows/bug.md): observed behavior contradicts an
     expectation.
   - [Task](references/workflows/task.md): maintenance, dependencies,
     configuration, documentation, refactoring, or operations that are neither
     Feature nor Bug.

4. Resume the first unmet stage using its linked contract and existing evidence;
   do not restart satisfied methods. Workflow files alone define stage order,
   transitions, and correction routes. At material checkpoints, identify
   **Human decision**, **Agent evidence**, and **Remaining uncertainty** in the
   existing artifact or response. Keep summaries proportional and omit trivial
   boilerplate; the Review stage owns review handoffs and evidence requirements.
5. Record the contract, evidence, approval, and delivery state using existing
   surfaces. For remote synchronization, use the relevant platform mapping:

   - [GitHub](references/platforms/github.md): mapped repository, Issue,
     Project, and existing pull-request records.

6. Hand missing engineering work to its execution owner with the authorized
   contract, approved decisions and steps, instructions and quality standards,
   evidence, and remaining gate. The owner investigates options and established
   native/library/local patterns, chooses and discloses routine defaults, and
   presents unsettled material choices for human decision. Continue independent
   authorized preparation while dependent work waits. For supplied method
   evidence, use the installed integration:

   - [Superpowers](references/integrations/superpowers.md): engineering-method
     evidence supplied to tracking gates.

7. Synchronize authorized tracking changes. Advance within scope only when
   evidence and approvals satisfy the gate; report unmet decisions, approvals,
   or blocked steps.

## Output

Work type, gate, changed records, final evidence and uncertainty, human decisions,
approval and delivery state, and smallest next action or handoff. Keep artifacts
concise, linking the interfaces or passages needing human judgment.

## Rules

- Track edits tracking records and artifact metadata. It does not implement,
  debug, review code, run engineering checks, commit, push, create pull
  requests, select executors or reviewers, or dispatch tasks. A handoff does not
  authorize dispatch.
- Keep early exploration in chat and proportional artifacts in their owning
  repository; move or retire misplaced artifacts. Unresolved ownership stays in
  chat or a cross-repository planning surface. Bounded, low-risk Design and Plan
  may stay inline when policy and intent permit; a gate alone requires no
  artifact, record, branch, or worktree. Temporary artifacts are not canonical
  docs.
- Remote tracking requires an owning surface and applicable policy, human
  direction, or existing owned tracking; explicit opt-out wins. Missing optional
  records or plugins require no setup and do not block work.
- Latest restrictions win. Access, drafts, status, and silence are not approval.
  Reuse settled authorization; preserve execution, review, commit, push, and
  delivery-record scope, including grants covered by an approved delivery route.
- Substantive work has material product, architecture, contract, ownership,
  security, or scope choices, or a nontrivial implementation needing settled
  design and steps. Routine low-risk work with a settled solution stays direct
  unless human direction or repository policy requires gates. Reversibility
  alone does not make a material choice routine. Explicit direction and stricter
  applicable policy win; reopen only materially affected approvals.
- Tracking state is not proof. Obtain missing or stale evidence from the
  execution context; never weaken a failed check or expand scope to pass a gate.
