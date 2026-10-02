---
name: write
description: Use when creating, refreshing, relocating, or reconciling documentation and verified knowledge in an owned destination.
---

# Write

Put verified content in its proper owner and integrate it with what is already
there. Locus owns placement and structure; the caller's writing style owns prose.

## Input

Requested content or evidence, destination, document scope, and nearest instructions.
Use `locus:find` when the owner or source is unclear.

| Operation | Contract |
| --------- | -------- |
| Create | Create selected missing documents; refresh any selected document that already exists. |
| Refresh | Default for existing documents: preserve useful content and custom sections, map them to the matching template's purpose and order. |
| Replace | Explicit request for exact named documents: rebuild from the matching template, report useful or uncertain content that will be discarded, and resolve ambiguous scope before replacing. |

Detection and advice requests return proposed placements without writing.

## Ownership

| Surface | Content |
| ------- | ------- |
| README.md | Human entrypoint: purpose, shortest working start, source navigation, owner links. |
| AGENTS.md | Working instructions: boundaries, routing, commands, checks, source/generator rules. |
| docs/README.md | Documentation index: subjects and one-line owner links. |
| docs/AGENTS.md | Instructions for maintaining docs and their sources. |
| ARCHITECTURE.md at the repository root | Standard architecture overview: system boundaries, components, flows, constraints, and design sources. |
| Topic pages under docs/ | Explanations, architecture, reference contracts, guides, durable decisions. |
| Code, tests, configuration | Runtime behavior, executable expectations, configuration truth. |
| Drafts, specs, plans | Temporary proposals and work contracts with explicit approval state. |
| Skills, scripts, hooks | Reusable procedures and deterministic automation. |
| Vault notes | Knowledge in the narrowest established topic or lane. |

README and AGENTS are entrypoints, not topic documentation. Link to the topic
owner instead of copying explanations or configuration reference into them.

## Workflow

1. Read the current owner and verify claims against their sources. Distinguish
   agreed intent from implemented behavior; treat chat and memory as leads.
2. Select the relevant reference for document creation or structural refresh:

   | Destination | Reference |
   | ----------- | --------- |
   | Repository root or package entrypoints | [repository.md](references/repository.md) |
   | Documentation index, instructions, or topic page | [documentation.md](references/documentation.md) |
   | Vault root, lane, or note | [vault.md](references/vault.md) |

   For a focused passage update, use the ownership table without loading templates.
3. Reconcile the smallest coherent passage. Merge overlap, preserve valid
   constraints and provenance, and remove superseded text. Update the generator
   when it owns the output. Create missing documents only when they serve the request.
4. Check affected facts, links, commands, examples, and generated output together.

## Output

Changed owners and paths, operation, what was reconciled, verification, and
unresolved facts or decisions. For Replace, identify material discarded content.
For detection or advice, return placements without writing.

## Rules

- Preserve authorized scope. If moving detail requires a destination outside
  named editable files, propose the move and keep the content pending authorization.
- Templates supply structure, not facts. Keep applicable headings in template
  order and useful custom sections; omit unused optional sections. The standard
  architecture template retains all eight numbered sections.
- New repository topic docs default to `docs/`; standard `ARCHITECTURE.md` belongs
  only at the repository root, never at a package or plugin boundary. Follow
  explicit destinations and existing declared owners; relocate only within
  authorized scope. Retain established vault organization.
- Do not turn a knowledge update into runtime, configuration, or work-record
  changes. Use the owning engineering or tracking workflow for those changes.
