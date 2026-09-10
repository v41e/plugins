---
name: operate
description: Use when authorized engineering or canonical documentation work must be executed and verified in its owning project context.
---

# Operate Authorized Work

Complete verified, authorized work in its owning execution context.

## Input

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
5. Follow the selected mode's implementation, verification, and delivery steps.

## Output

Use the selected mode's output contract.

## Rules

- Work only inside the caller-authorized owning execution context. Never list
  saved projects, create tasks, or edit unrelated projects.
- Missing, inaccessible, or truncated evidence is **Unknown** or **Partial**,
  never green.
- Drafts and ideas do not authorize implementation.
- Silence and comment counts prove nothing. Use explicit approval evidence;
  the latest human restriction wins.
- Commit, push, or open a PR only when permitted by the request and repository
  policy. Never merge, release, deploy, create schedules, or mutate live
  automations.
