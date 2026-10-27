# Iter Workflows

Iter connects observations, work records, maintenance, and authorized dispatch.
Each skill has one owner; engineering methods remain in the project context.

| Skill | Owns | Result |
| ----- | ---- | ------ |
| [Brief](../skills/brief/SKILL.md) | Read-only judgment from goals, decisions, and selected evidence | Status, focus plan, or retrospective |
| [Track](../skills/track/SKILL.md) | Work contracts, approvals, evidence gates, and synchronization | Current state and missing evidence or handoff |
| [Maintain](../skills/maintain/SKILL.md) | Candidate selection, reconciliation, continuation, and stopping in an authorized owner | Verified repairs, documentation corrections, or a supported no-op |
| [Orchestrate](../skills/orchestrate/SKILL.md) | Authorized sequential dispatch to exact project-owned tasks | Owning task references and aggregate outcomes |

Track can be used directly for manual work. It records the results of
engineering methods such as Superpowers; it does not implement, debug, review
code, or deliver changes. New Feature, Bug, and Task work starts in a local
draft before authorized Issue publication. Work arriving through an existing
Issue uses that contract and resumes the first unmet gate; it needs no duplicate
draft. Optional Projects and fields require no setup. Pending synchronization
remains explicit and useful local artifacts stay actionable.

Maintain checks signals against current state and existing ownership before
choosing work. An already owned outcome is resumed only when it belongs to this
assignment; another owner's work stays with that owner. Locus Find and Write can
help resolve content ownership and reconcile documentation when installed.

## Supervised Work

The owning copilot investigates and recommends within the agreed outcome,
chooses routine implementation details, and brings unsettled material decisions
to the human. Caller instructions and repository policy supply review, metadata,
and delivery requirements; Iter preserves their authority.

[Track](../skills/track/SKILL.md) records the selected workflow's gates:

- [Feature](../skills/track/references/workflows/feature.md) reviews its draft,
  specification, plan, and implementation, with distinct scope, design, and
  execution approvals.
- [Task](../skills/track/references/workflows/task.md) and
  [Bug](../skills/track/references/workflows/bug.md) establish a lightweight
  contract in Scope or Triage, then review it before implementation. The
  contract can be a local draft or an existing Issue; current review and
  approvals are reused. There is no automatic spec/plan pipeline.
- [Review](../skills/track/references/stages/review.md) repeats within each
  material stage: author, fresh review, supported corrections, then review
  again. Ready evidence reaches the applicable human checkpoint; missing
  evidence or the caller's retry limit holds progress. Optional Bug/Task specs
  and plans follow the same loop without adding Feature approval stages.
- [Record synchronization](../skills/track/SKILL.md#record-synchronization)
  reconciles the agreed local and remote owners without overwriting conflicts or
  treating pending writes as complete.

Workflows own stage relationships; stages own evidence requirements and adapters
map capabilities. Useful local artifacts remain until their content and approved
snapshots are safely represented in their owners.

## Interactive Goals

Native Goals and separately authorized same-chat follow-ups compose with
existing skills through the
[Track Codex mapping](../skills/track/references/harnesses/codex.md). Brief
supports read-only focus; Track records state; the owning execution context
performs research, review, and approved work. Orchestrate remains the distinct
route for authorized sequential project-chat dispatch. No coordinator or runtime
is bundled.

## Signals and Harnesses

A timer or supported event can supply a repository, resource link, revision or
run identity, and time. The caller's standing assignment supplies scope and
authority. A signal alone supplies neither. Stale or superseded signals may
produce a no-op; repeated signals reuse the same unfinished owning assignment.

Signal intake remains with the caller. Orchestrate receives affected owners and
assignments rather than scanning repositories for work. Periodic documentation
reconciliation and targeted repair can use the same maintenance skill. No event
receiver, polling service, or schedule is bundled.

Workflows keep harness mappings inside their owning skill. The
[Brief Codex mapping](../skills/brief/references/harnesses/codex.md) covers
read-only evidence; the
[Orchestrate Codex adapter](../skills/orchestrate/references/harnesses/codex.md)
covers project/task discovery, inspection, creation, continuation, and waiting.
Another harness needs equivalent verified capabilities before dispatch can run.
