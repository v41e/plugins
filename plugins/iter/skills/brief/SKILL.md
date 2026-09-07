---
name: brief
description: Use when preparing a read-only status brief, plan, or retrospective for one current Git repository.
---

# Brief One Repository

Report verified repository state without coordinating saved projects or doing
the work.

## Input

Require one mode, the current repository, and one `window`. The window may be
explicit or relative. Resolve the IANA timezone from the caller or runtime.
Capture `as_of` once as the reference time used to resolve every relative
window consistently.

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
2. Establish the repository root, then read the nearest `AGENTS.md` and
   `CONTRIBUTING.md`:

   ```sh
   git rev-parse --show-toplevel
   ```

3. Resolve relative windows against `as_of`. Convert named-zone calendar
   boundaries to explicit half-open instants `[start, end)` with local offsets
   and UTC equivalents. Let the timezone database determine each boundary's
   offset; never assume every local day is 24 hours.
4. Gather remote evidence before local Git or work artifacts. Resolve the
   configured provider here and read its adapter plus only the references it
   routes to for the selected mode:

   | Provider | Adapter                                     |
   | -------- | ------------------------------------------- |
   | GitHub   | [github.md](references/platforms/github.md) |

   If the provider is missing, unsupported, or ambiguous, mark remote coverage
   **Unknown**. Preserve source coverage and reconcile superseded evidence.

5. Gather local evidence only after the remote pass:

   ```sh
   git status --short --branch
   git log --since-as-filter=START_UTC --until=END_UTC --format='%H%x09%cI%x09%s'
   ```

   Apply the exact `[start, end)` filter to emitted committer timestamps so a
   commit at `end` is excluded; use `--since` if `--since-as-filter` is not
   supported. Inspect owned drafts, specs, and plans when present. Do not run a
   historical Git log against a future planning horizon; use only `lookback`
   for past activity in `plan`. A dirty file is current state, not recent work.

6. Reconcile newer evidence, distinguish current state from interval activity,
   then follow the selected mode's output contract.

## Output

State the repository, mode, `as_of`, timezone, normalized local and UTC
intervals, and evidence coverage. Separate verified facts, inferences,
unknowns, proposals, and human decisions.

## Rules

- One current repository only. Never list saved projects or dispatch tasks.
- Remain read-only; do not mutate files, Git, remote records or metadata,
  tasks, schedules, automations, or live systems.
- Current open backlog is a live observation. If `as_of` is in the past, never
  present today's open state as the exact state at that earlier instant.
- Missing, inaccessible, or truncated evidence is **Unknown** or **Partial**,
  never green.
- A draft, artifact, Project status, or Issue proves approval only when explicit
  approval evidence says so.
- Never infer release, deployment, impact, ownership, or commitment.
