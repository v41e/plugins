---
name: operate
description: Use when authorized engineering or canonical documentation work must be executed and verified in one current Git repository.
---

# Operate One Repository

Complete verified, authorized work in the current repository.

## Input

Require one mode, the current repository, and an action boundary defined by the
request, explicit approval, an already authorized active task, or an authorized
maintenance pass.

| Mode            | Outcome                               | Reference                                             |
| --------------- | ------------------------------------- | ----------------------------------------------------- |
| `engineering`   | Diagnose, fix, test, and deliver code | [engineering.md](references/modes/engineering.md)     |
| `documentation` | Align owned canonical documentation   | [documentation.md](references/modes/documentation.md) |

## Workflow

1. Read the selected mode completely. Establish the repository root and local
   state:

   ```sh
   git rev-parse --show-toplevel
   git status --short --branch
   ```

2. Read the nearest `AGENTS.md` and `CONTRIBUTING.md`. Preserve unrelated work.
   Inspect approved work artifacts when present.
3. Gather remote evidence. Resolve the configured provider here and read its
   adapter plus only the references it routes to for the selected mode:

   | Provider | Adapter                                     |
   | -------- | ------------------------------------------- |
   | GitHub   | [github.md](references/platforms/github.md) |

   If the provider is missing, unsupported, or ambiguous, mark remote coverage
   **Unknown**. When local task ownership matters and desktop task tools are
   available, inspect only tasks for this repository; incomplete enumeration is
   **Unknown**.

4. Verify authorization and absence of conflicting active work. For defect-driven
   work, reproduce the failure before changing files. For additive work, establish
   the approved acceptance criteria before changing files.
5. At implementation, read the
   [Superpowers adapter](references/integrations/superpowers.md) only when its
   installed skills match observed conditions.
6. Follow the selected mode, implement the smallest complete change, run the
   applicable repository checks, and follow repository Git delivery policy.

## Output

Follow the selected mode. Report evidence, changed files or verified no-op,
checks with results, delivery performed, skipped candidates, blockers, and
human decisions.

## Rules

- One current repository only. Never list saved projects, create Codex tasks,
  or coordinate other repositories.
- Missing, inaccessible, or truncated evidence is **Unknown** or **Partial**,
  never green.
- Drafts and ideas do not authorize implementation.
- Resume approved work only with explicit approval, clear ownership, and no
  conflicting task or PR.
- Comment count or absence never determines eligibility. Explicit human
  approval or pause in a comment is evidence; the latest human restriction
  overrides older approval.
- Commit, push, or open a PR only when permitted by the request and repository
  policy. Never merge, release, deploy, create schedules, or mutate live
  automations.
