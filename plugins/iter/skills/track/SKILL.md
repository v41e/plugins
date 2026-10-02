---
name: track
description: Use when repository work needs classification, resumption, approval and evidence tracking, or record synchronization.
---

# Track

Keep work contracts, approvals, evidence, and delivery state proportional and
resumable. Superpowers or the owning context supplies engineering methods.

## Input

Latest human intent, current repository state and instructions, work contracts,
approval evidence, local artifacts, and optional remote records.

## Workflow

1. Establish ownership, Git state, contribution policy, and existing records.
   Follow explicit links first; use installed `locus:find` only when ownership
   or active work remains unclear.
2. Compare current intent and repository evidence with tracked state. Reuse
   settled decisions and approvals; update or retire stale artifacts and return
   to the earliest affected gate after a material change.
3. Classify Feature, Bug, or Task and read the paths, shared controls, and current
   gate in [lifecycle.md](references/lifecycle.md). Resume the first unmet gate.
4. Record the contract, evidence, approval, and delivery state using existing
   surfaces. When GitHub synchronization applies, read the
   [GitHub adapter](references/platforms/github.md).
5. For missing engineering work, give the owning execution context the contract,
   current gate, authorization, and missing evidence. When Superpowers is
   installed, use its [evidence bridge](references/integrations/superpowers.md).
6. Synchronize authorized tracking changes and advance when evidence and
   approvals satisfy the gate. Report remaining handoffs or gates.

## Output

Work type, current gate or transition, changed records, evidence, approval and
delivery state, and smallest next action or execution handoff.

## Rules

- Track edits tracking records and artifact metadata. It does not implement,
  debug, review code, run engineering checks, commit, push, create pull requests,
  select executors, or dispatch tasks.
- Latest restrictions win. Access, drafts, status, and silence are not approval;
  preserve execution, review, commit, push, and delivery-record grants separately.
- Missing plugins or formal records require no setup or replacement engineering
  itinerary. Keep unresolved gates explicit.
