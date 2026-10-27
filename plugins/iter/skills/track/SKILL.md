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

Caller instructions and repository policy govern reviewer selection, evidence
location, retry budget, metadata owners, and execution/delivery authority across
stages. Preserve stricter requirements and existing grants.

For caller-supplied native Goal or scheduled-wakeup context, read the
[Codex mapping](references/harnesses/codex.md) when applicable.

## Workflow

1. Establish ownership, Git state, contribution policy, and existing records.
   Preserve the selected checkout and unrelated changes. Follow explicit links;
   use installed `locus:find` only when ownership or active work remains
   unclear.
2. Reconcile intent and repository evidence with tracked state. Expose material
   changes since approval and return to the earliest affected gate; reuse
   unaffected approvals. Consolidate duplicate records and split independently
   prioritizable outcomes when useful. Preserve actionable local artifacts;
   Complete owns their retirement. Interpret mixed feedback per outcome:
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
   do not restart satisfied methods. Workflow files define stage order,
   transitions, and correction routes; stages own their evidence requirements.
5. Use the existing Issue as the work contract. For new work without an Issue,
   prepare a concise local draft under `docs/superpowers/drafts/` or its
   supplied owner before publication. Keep additional local notes, specs, or
   plans only when useful or requested; an existing Issue needs no duplicate
   draft. After applicable scope approval, create or update the Issue when
   authorized; pending synchronization does not block authorized local work.
   Record evidence, approval, and delivery state in their existing owners. For
   remote writes, use the relevant platform mapping:

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

### Record Synchronization

Use the agreed local and remote metadata owners, scales, and record links. For
local draft/spec/plan formatting, read
[artifact metadata](references/metadata.md). Specs and plans link their
predecessors instead of duplicating metadata.

When the caller maintains the same fields on both surfaces, compare each with
its last confirmed value. Synchronize authorized one-sided or matching changes;
ask about incompatible changes or differing values with unknown provenance.
Establish a missing baseline only from matching values or authorized
initialization and readback. Preserve pending values and advance the baseline
only after verified agreement; a different linked record needs its own baseline.

## Output

Work type, gate, changed records, final evidence and uncertainty, human
decisions, approval and delivery state, and smallest next action or handoff.
Keep artifacts concise, linking the interfaces or passages needing human
judgment.

## Rules

- Track edits tracking records and artifact metadata. It does not implement,
  debug, review code, run engineering checks, commit, push, create pull
  requests, select executors or reviewers, or dispatch tasks. A handoff does not
  authorize dispatch.
- Keep early exploration in chat and proportional artifacts in their owning
  repository; move or retire misplaced artifacts. Unresolved ownership stays in
  chat or a cross-repository planning surface. Bounded, low-risk Design and Plan
  may stay inline when policy and intent permit; a gate alone requires no extra
  artifact, branch, or worktree. Temporary artifacts are not canonical docs.
- Remote writes require an owning surface and authorization. Explicit local-only
  direction wins: retain useful local artifacts and pending synchronization
  without pretending records are synced. Optional Projects, fields, or plugins
  require no setup and do not block authorized local work.
- Latest restrictions win. Access, drafts, status, and silence are not approval.
  Reuse settled authorization and distinguish execution from delivery authority.
  Merge and release remain separate grants.
- Substantive work has material product, architecture, contract, ownership,
  security, or scope choices, or a nontrivial implementation needing settled
  design and steps. Routine low-risk Bugs and Tasks with a settled solution need
  no additional spec/plan gates unless required by human direction or repository
  policy. Reversibility alone does not make a material choice routine; reopen
  only materially affected approvals.
- Tracking state is not proof. Obtain missing or stale evidence from the
  execution context; never weaken a failed check or expand scope to pass a gate.
