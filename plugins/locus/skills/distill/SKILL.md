---
name: distill
description: Use when work or conversations reveal durable knowledge to place or promote, or overlapping guidance needs reconciliation.
---

# Distill

Distill the smallest verified durable signal into its narrowest owner.

## Input

- Evidence, requested action, selected destination, and nearest `AGENTS.md`.
- Relevant code, tests, docs, configuration, or linked work records.

Recalled facts in chat and memory are discovery leads to verify against their
owner. Current explicit user decisions establish intent; record them separately
from implemented behavior.

## Route

| Owner                      | Knowledge                                                                     |
| -------------------------- | ----------------------------------------------------------------------------- |
| Code                       | Runtime behavior                                                              |
| Tests                      | Executable expectations                                                       |
| `README.md`, `docs/`       | Stable intent, architecture, constraints, usage, and durable depth            |
| `AGENTS.md`                | Concise local semantics for action: entrypoint, routing, boundaries, commands |
| Owned tool docs and config | Tool capabilities, requirements, and constraints                              |
| Skills                     | Reusable judgment-driven workflows                                            |
| Scripts                    | Explicit deterministic operations                                             |
| Hooks                      | Automatically triggered context, checks, or enforcement                       |

Drafts, remote work records, and releases are evidence or provenance, not
default destinations. Update them only when explicitly requested through their
owning workflow.

## Workflow

1. Extract each independent durable signal; reject speculation, duplication,
   and temporary narration.
2. Read its current owner and verify each claim against the surface owning that
   dimension. Resolve contradictions from that evidence; continue independent
   verified signals when one needs human judgment.
3. Retrieve missing local or remote evidence with `locus:find`.
4. Prefer the nearest existing destination. Create the smallest necessary new
   document within an authorized update only when ownership and placement are
   verified; use `locus:init` when its repository or vault target and canonical
   document contract apply. Promote the signal once.
5. Preserve provenance for external, time-sensitive, or historical claims.
6. A requested update authorizes reconciliation of its verified subject and
   scope. Rewrite the smallest coherent passage, merging overlapping guidance
   and removing superseded text. Preserve valid constraints, unresolved
   decisions, and explicit approval gates.

## Output

Return one compact record per signal: status, one action, owner and path when
applicable, one-line summary, provenance when relevant, and verification for a
write. When the user requests promotion advice without authorizing writes,
return proposals only.

| Status                 | Use when                                                                                                 |
| ---------------------- | -------------------------------------------------------------------------------------------------------- |
| `updated`              | An authorized update was applied to a verified existing owner                                            |
| `created`              | An authorized destination was created at a verified placement                                            |
| `already-known`        | The verified owner already contains the signal                                                           |
| `update-needed`        | The signal and owner path are verified, but no write occurred                                            |
| `wrong-place`          | The signal exists outside its verified owner                                                             |
| `too-weak`             | The evidence is speculative or insufficient                                                              |
| `needs-human-judgment` | Meaning, ownership, placement, a material undelegated decision, or required authority remains unresolved |

## Rules

- Default to detection unless the user requested an update.
- If a useful note is incomplete and the destination exposes an inbox or review
  area, return `update-needed` and name it.
- If placement cannot be verified, return `needs-human-judgment` instead of
  inventing a destination.
- Use `wrong-place`, not `update-needed`, when the verified signal currently
  exists outside its owner.
