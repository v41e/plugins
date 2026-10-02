---
name: write
description: Use when creating, refreshing, relocating, or reconciling documentation and verified knowledge in an owned destination.
---

# Write

## Purpose

Put verified content in its proper owner and integrate it with what is already
there. Locus owns placement and structure; the caller's writing style owns prose.

## Input

Requested content or evidence, destination, document scope, editing instructions,
and nearest local instructions. Use `locus:find` when the owner or source is unclear.

## Workflow

### Ownership

| Surface | Content |
| ------- | ------- |
| README.md; `packages/**/README.md` | Human entrypoints: purpose, shortest working start, source navigation, owner links. |
| AGENTS.md; `packages/**/AGENTS.md` | Working instructions: boundaries, routing, commands, checks, source/generator rules. |
| docs/README.md | Documentation index: subjects and one-line owner links. |
| docs/AGENTS.md | Instructions for maintaining docs and their sources. |
| ARCHITECTURE.md | Standard architecture overview: system boundaries, components, flows, constraints, and design sources. |
| Topic pages under docs/ | Explanations, architecture, reference contracts, guides, durable decisions. |
| Code, tests, configuration | Runtime behavior, executable expectations, configuration truth. |
| Drafts, specs, plans | Temporary proposals and work contracts with explicit approval state. |
| Skills, scripts, hooks | Reusable procedures and deterministic automation. |
| Vault notes | Knowledge in the narrowest established topic or PARA lane. |

README and AGENTS are entrypoints, not topic documentation. The same ownership
applies to other package or plugin boundaries. Link to the topic owner instead
of copying explanations or configuration reference into them.

1. Read the current owner and verify claims against their sources. Distinguish
   agreed intent from implemented behavior; treat chat and memory as leads.
2. For creation or structural refresh, use the selected target and its templates:

   | Destination | Reference |
   | ----------- | --------- |
   | Repository root or package entrypoints | [repository.md](references/targets/repository.md) |
   | Documentation index, instructions, or topic page | [documentation.md](references/targets/documentation.md) |
   | Vault root, lane, or note | [vault.md](references/targets/vault.md) |

   Focused passage updates use the ownership table and existing document structure.
3. Default to reconciling the smallest coherent passage. Merge overlap, preserve
   useful custom sections, valid constraints, and provenance; remove superseded text. Create
   selected missing documents when needed. Explicit replacement applies only to
   named documents: identify useful or uncertain content it would discard and
   resolve ambiguous scope before replacing. Detection, advice, and dry runs return
   placements without writing. Update the generator when it owns the output.
4. Check affected facts, links, commands, examples, and generated output together.

## Output

Changed owners and paths, what was reconciled, verification, and unresolved facts
or decisions. Identify material discarded content for an explicit replacement;
return proposed placements for detection, advice, or dry runs.

## Rules

- Preserve authorized scope. If moving detail requires a destination outside
  named editable files, propose the move and keep the content pending authorization.
- Templates supply structure, not facts. Keep applicable headings in template
  order and useful custom sections; remove authoring notes and unused optional
  sections. The standard architecture template retains all eight numbered sections.
- New repository topic docs default to `docs/`. Follow explicit destinations and
  existing declared owners; relocate only within authorized scope. Preserve
  established vault organization unless migration or structural reset is requested.
- Use the owning engineering or tracking workflow for runtime, configuration,
  or work-record changes.
