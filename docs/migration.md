# Skill Migration

The refactor separates content placement, work tracking, maintenance, and
dispatch. These names replace the previous callable skills; aliases are not
bundled.

| Previous call | Current call | Responsibility |
| ------------- | ------------ | -------------- |
| `locus:init` | `locus:write` | Create or refresh content in its verified owner |
| `locus:distill` | `locus:write` | Reconcile durable knowledge into its owner |
| `locus:track` | `iter:track` | Work records, approvals, evidence gates, and synchronization |
| `iter:operate` | `iter:maintain` | Bounded engineering or documentation maintenance |

`locus:find`, `iter:brief`, and `iter:orchestrate` retain their names. Concise Using
inventories describe the available skills. Track belongs to Iter and adds
tracking over the owning engineering methods; it does not execute those methods
or deliver code.

## Caller rollout

Update matching instructions, prompts, and automation callers with the names
above. Preserve existing scope, gates, delivery grants, cadence, destination,
model, notifications, and conversation continuity. Changing a skill name does
not authorize a new assignment or broaden an existing one.

Source edits do not update installed plugin copies. Refresh the installation
through the client and reload plugins before using the new calls. Source
validation does not establish that an installed copy or live automation has
been migrated.

Locus now owns location and useful structural slots. README and AGENTS are
entrypoints and instructions; topic explanations belong in their canonical
documentation owner, under `docs/` for new repository documentation. Caller
writing style remains independent. Existing declared owners and generated
surfaces follow the [Write contract](../plugins/locus/skills/write/SKILL.md).

Iter keeps [distinct workflow owners](../plugins/iter/docs/workflows.md). Brief
may discover and read across requested projects; only authorized Orchestrate
requests create or continue project tasks. Signals, access, and existing task
titles do not establish dispatch authority.
