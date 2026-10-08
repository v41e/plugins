# Iter Workflows

Iter connects observations, work records, maintenance, and authorized dispatch.
Each skill has one owner; engineering methods remain in the project context.

| Skill | Owns | Result |
| ----- | ---- | ------ |
| [Brief](../skills/brief/SKILL.md) | Read-only judgment from goals, decisions, and selected evidence | Status, focus plan, or retrospective |
| [Track](../skills/track/SKILL.md) | Work contracts, approvals, evidence gates, and synchronization | Current state and missing evidence or handoff |
| [Maintain](../skills/maintain/SKILL.md) | Candidate selection, reconciliation, continuation, and stopping in an authorized owner | Verified repairs, documentation corrections, or a supported no-op |
| [Orchestrate](../skills/orchestrate/SKILL.md) | Authorized sequential dispatch to exact project-owned tasks | Owning task references and aggregate outcomes |

Track can be used directly for manual work. It records the results of engineering
methods such as Superpowers; it does not implement, debug, review code, or deliver
changes. Required records and artifact depth follow the current contract and
repository policy. Missing optional records require no setup.

Maintain checks signals against current state and existing ownership before
choosing work. An already owned outcome is resumed only when it belongs to this
assignment; another owner's work stays with that owner. Locus Find and Write can
help resolve content ownership and reconcile documentation when installed.

## Supervised work

The owning copilot investigates and recommends within the agreed outcome.
Compare native/library capabilities, workload, and established local patterns
before adding machinery. Choose routine defaults and disclose consequential
assumptions; present unsettled material product, architecture, contract,
ownership, security, and scope choices for a focused human decision. A reversible
choice can still be material. Questions and exploration do not grant execution;
continue independent authorized preparation while dependent choices wait.

[Track](../skills/track/SKILL.md) records the selected workflow's gates:
[Feature](../skills/track/references/workflows/feature.md) uses the same Review
contract for its draft, specification, plan, and implementation. Idea review and
summary stay quick for early human feedback. [Task](../skills/track/references/workflows/task.md)
and [Bug](../skills/track/references/workflows/bug.md) settle their problem,
solution, and authority through proportional evidence and discussion, then review
the implementation; they do not automatically inherit draft/spec/plan approvals.
Workflows own all stage relationships; stages describe their own responsibilities.

[Review](../skills/track/references/stages/review.md) records independent evidence,
supported corrections, a concise identified-artifact summary, and the human
decision required by the workflow. The execution context obtains suitable review
against original intent, accepted decisions, and relevant local examples; checks
alone do not prove alignment. Approved execution scope can cover PR publication
after checks/review without another discretionary checkpoint. Explicit holds,
human PR review/integration, and actual integrated-result verification still bind.
Reuse unaffected approvals and equivalent evidence; summary approval adds no
mandatory full-artifact reading gate.

## Interactive Goals

Native Goals and separately authorized same-chat follow-ups compose with existing
skills through the [Track Codex mapping](../skills/track/references/harnesses/codex.md).
Brief supports read-only focus; Track records state; the owning execution context
performs research, review, and approved work. Orchestrate remains the distinct
route for authorized sequential project-chat dispatch. No coordinator or runtime
is bundled.

## Signals and harnesses

A timer or supported event can supply a repository, resource link, revision or
run identity, and time. The caller's standing assignment supplies scope and
authority. A signal alone supplies neither. Stale or superseded signals may
produce a no-op; repeated signals reuse the same unfinished owning assignment.

Signal intake remains with the caller. Orchestrate receives affected owners and
assignments rather than scanning repositories for work. Periodic documentation
reconciliation and targeted repair can use the same maintenance skill. No event
receiver, polling service, or schedule is bundled.

Workflows keep harness mappings inside their owning skill. The
[Brief Codex mapping](../skills/brief/references/harnesses/codex.md) covers read-only
evidence; the [Orchestrate Codex adapter](../skills/orchestrate/references/harnesses/codex.md)
covers project/task discovery, inspection, creation, continuation, and waiting.
Another harness needs equivalent verified capabilities before dispatch can run.
