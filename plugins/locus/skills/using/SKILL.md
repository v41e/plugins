---
name: using
description: Use when choosing a Locus skill for finding or placing owned content.
---

# Using Locus

## Input

Requested outcome, known owner, and whether a content update is requested.

## Workflow

| Need | Route |
| ---- | ----- |
| Locate content, sources, or work context | `locus:find` |
| Create, refresh, relocate, or reconcile content | `locus:write` |
| Track repository work | `locus:track` |

For orientation, explain the route here. For requested action, read the matching
skill. Find first only when the owner or evidence is unclear.

## Output

Selected route, owner when known, and any unresolved scope or authority.

## Rules

- Using routes; the selected skill performs the action.
- Content placement does not select writing style or authorize engineering work.
