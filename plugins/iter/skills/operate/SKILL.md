---
name: operate
description: Use when authorized engineering or canonical documentation needs one bounded run in its owning project context.
---

# Operate One Authorized Run

Complete one bounded, verified, authorized operation in its owning context.

## Input

- Run: one manual or scheduled invocation.
- Mode: engineering or documentation.
- Scope: owning execution context and authorized work.
- Authority: explicit request/approval, an authorized active task, or authorized maintenance pass.

| Mode            | Outcome                                | Reference                                             |
| --------------- | -------------------------------------- | ----------------------------------------------------- |
| `engineering`   | Implement, fix, test, and deliver code | [engineering.md](references/modes/engineering.md)     |
| `documentation` | Align owned canonical documentation    | [documentation.md](references/modes/documentation.md) |

## Workflow

1. Read the selected mode completely. Identify the owned sources in scope. For
   each local Git source, establish its root and state:

   ```sh
   git rev-parse --show-toplevel
   git status --short --branch
   ```

2. Read applicable `AGENTS.md`, `CONTRIBUTING.md`, and linked work artifacts.
   Preserve unrelated work. For Superpowers artifacts or matching installed
   skills, read the [Superpowers integration](references/integrations/superpowers.md).
3. Gather relevant remote evidence. For GitHub, read the
   [GitHub adapter](references/platforms/github.md) and its selected-mode references.
   Missing, unsupported, or ambiguous providers leave remote coverage **Unknown**.
   When ownership matters and task tools are available, inspect only matching
   work; incomplete enumeration is **Unknown**.
4. Confirm authorization, ownership, and no conflicting active work.
5. For tracked work, read its work and current-stage contracts, then resume using
   Locus Track when installed. Do not reclassify it or create
   replacement tracking. Otherwise complete the bounded operation under
   repository policy.
6. Follow the selected mode's steps inside that boundary.

## Output

Use the selected mode's output contract.

## Rules

- Work only inside the caller-authorized owning execution context. Never list
  saved projects, create tasks, or edit unrelated projects.
- Missing, inaccessible, or truncated evidence is **Unknown** or **Partial**,
  never green.
- Drafts and ideas do not authorize implementation.
- A run may address Feature, Bug, or Task work. Recurring invocation does not
  restart its lifecycle or create tracking.
- Silence and comment counts prove nothing. Use explicit approval evidence;
  the latest human restriction wins.
- Before commit, push, or PR creation, satisfy any required local human review of
  the verified uncommitted diff and material decisions. Access approval is not
  delivery authority. Preserve standing task-specific commit, push, and PR
  grants separately; newer restrictions override them.
- Perform permitted Git delivery in the selected worktree with configured
  signing. If Git metadata access or signing fails, request access only for the
  resolved Git common directory and worktree administration directory. If a
  granted scope is insufficient and the operation is already authorized, use
  the configured approval mechanism for that exact native Git operation. A hard
  denial stops delivery; never broaden or repeat escalation, switch repositories,
  reconstruct Git metadata, use remote APIs as a substitute, disable signing,
  or bypass the denial. Retain the reviewed diff and report the blocker.
- Never merge, release, deploy, create schedules, or mutate live automations.
