---
name: brief
description: Use when preparing a read-only status brief, focus plan, or retrospective from current project context.
---

# Brief Current Work

Report verified work state without coordinating tasks or doing the work.

## Input

- Modes: one or more from the table below.
- Scope: subject and sources from the request and project context.
- Window: explicit or relative.
- Timezone: caller or runtime IANA zone.
- `as_of`: capture once; resolve all relative windows against it.

| Mode            | Interpret `window` as                          | Reference                                             |
| --------------- | ---------------------------------------------- | ----------------------------------------------------- |
| `status`        | Historical `status_window`                     | [status.md](references/modes/status.md)               |
| `plan`          | Future `planning_horizon`; optional `lookback` | [plan.md](references/modes/plan.md)                   |
| `retrospective` | Historical `retrospective_window`              | [retrospective.md](references/modes/retrospective.md) |

Daily, weekly, and monthly are cadences, not modes. If an unattended request
omits a required input, return an incomplete-input result naming it; never
guess or wait indefinitely.

## Workflow

1. Read the selected mode completely.
2. Read project instructions, ownership, and source links. Non-Git contexts are
   valid. For each Git source, establish its root and read the nearest
   `AGENTS.md` and `CONTRIBUTING.md`:

   ```sh
   git rev-parse --show-toplevel
   ```

3. Resolve relative windows against `as_of`. Convert named-zone calendar
   boundaries to explicit half-open instants `[start, end)` with local offsets
   and UTC equivalents. Let the timezone database determine each boundary's
   offset; never assume every local day is 24 hours.
4. Gather relevant remote, local, task, and worktree evidence.
   For GitHub, read the [GitHub adapter](references/platforms/github.md) and
   only its selected-mode references. Missing, unsupported, or ambiguous
   providers leave remote coverage **Unknown**.

5. For local Git sources, use relevant commands such as:

   ```sh
   git status --short --branch
   git log --since-as-filter=START_UTC --until=END_UTC --format='%H%x09%cI%x09%s'
   ```

   Apply the exact `[start, end)` filter to emitted committer timestamps so a
   commit at `end` is excluded; use `--since` if `--since-as-filter` is not
   supported. Do not run a historical Git log against a future
   planning horizon; use only `lookback` for past activity in `plan`. A dirty
   file is current state, not recent work.

6. Follow project artifact links and conventions. For Superpowers artifacts,
   read the [Superpowers integration](references/integrations/superpowers.md).
7. Reconcile newer evidence, distinguish current state from interval activity,
   then follow the selected mode's output contract.

## Output

State the subject, mode, `as_of`, timezone, normalized local and UTC intervals,
and evidence coverage. Separate verified facts, inferences, unknowns,
proposals, and human decisions.

## Rules

- Work only within the current task and caller-provided project context. Do not
  create, continue, or dispatch tasks.
- Remain read-only; do not mutate files, Git, remote records or metadata,
  tasks, schedules, automations, or live systems.
- Current open backlog is a live observation. If `as_of` is in the past, never
  present today's open state as the exact state at that earlier instant.
- Missing, inaccessible, or truncated evidence is **Unknown** or **Partial**,
  never green.
- Approval requires explicit evidence, not artifact existence or status.
- Never infer release, deployment, impact, ownership, or commitment.
