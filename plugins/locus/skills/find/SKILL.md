---
name: find
description: Use when the user needs to locate relevant owned knowledge, active work, a repository, documentation, configuration, notes, or another knowledge destination.
---

# Find

## Purpose

Find the smallest verified context that can answer the task. Start locally and
broaden only when the task requires context outside local files.

## Input

- The user's request and any explicit path, issue, or pull request.
- The current repository and nearest `AGENTS.md`.

## Workflow

1. Select an explicitly named path, issue, or pull request first.
2. For local context, read applicable `AGENTS.md` files from the repository root
   to the selected owner. At each level, follow only the matching immediate child
   and continue through nested boundaries when needed.
3. Read only the selected owner's relevant code, tests, `README.md`, or `docs/`.
4. Follow issue or pull-request links from the selected local artifact when
   needed to answer the original question, regardless of remote state.
5. Resolve any missing non-local context through the relevant mapping:

   | When | Capability | Result |
   | ---- | ---------- | ------ |
   | Remote work or delivery context is needed | [GitHub](references/platforms/github.md) | Work contract, coordination, or review evidence |
   | The owner is outside the current repository | [Knowledge map](references/platforms/knowledge-map.md) | Candidate destination to verify locally |

   A map may locate the owner before GitHub supplies its work context. Verify
   that owner's local sources; broaden again only if the question remains unanswered.
6. Stop as soon as the minimum verified owner set answers the task.

## Output

Return the best pointer, why it matches, the minimum verified context, and the
smallest useful next action. When asked about tracked work, state whether it is
active and whether resumption is warranted. When ambiguous, return a few compact
pointers.

## Rules

- Keep retrieval read-only; do not create, edit, or distill knowledge.
- Treat chat, memory, and map entries as discovery leads; verify facts against
  the selected owner.
- Parent instructions own routing and shared rules; the selected owner supplies
  local facts. Sibling packages, the whole map, and unrelated history need a
  reason in the original question.
- Return any tracked-work next action to `iter:track` when installed.
- If nothing matches clearly, say that instead of guessing.
