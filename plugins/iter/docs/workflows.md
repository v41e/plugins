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

## Signals and harnesses

A timer or supported event can supply a repository, resource link, revision or
run identity, and time. The caller's standing assignment supplies scope and
authority. A signal alone supplies neither. Stale or superseded signals may
produce a no-op; repeated signals reuse the same unfinished owning assignment.

Signal intake remains with the caller. Orchestrate receives affected owners and
assignments rather than scanning repositories for work. Periodic documentation
reconciliation and targeted repair can use the same maintenance skill. No event
receiver, polling service, or schedule is bundled.

Workflows use available harness capabilities. The shared [Codex adapter](../references/harnesses/codex.md)
maps project/task discovery, inspection, creation, continuation, and waiting.
Brief uses its read capabilities; Orchestrate uses authorized dispatch. Another
harness needs equivalent verified capabilities before dispatch can run.
