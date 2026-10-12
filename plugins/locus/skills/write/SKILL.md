---
name: write
description: Use when creating, refreshing, relocating, or reconciling documentation and verified knowledge in an owned destination.
---

# Write

## Purpose

Reconcile verified content in its proper owner. Locus owns placement and
structure; preserve the caller's writing style.

## Input

Requested content or evidence, destination, document scope, editing
instructions, and nearest local instructions. Use `locus:find` when the owner or
source is unclear.

## Workflow

### Ownership

| Surface | Content |
| ------- | ------- |
| README.md; `packages/**/README.md` | Human entrypoints: purpose, shortest working start, source and owner navigation. |
| AGENTS.md; `packages/**/AGENTS.md` | Working instructions: boundaries, routing, commands, checks, source/generator rules. |
| docs/README.md | Documentation entrypoint: Overview, Structure, one-line owner links. |
| docs/AGENTS.md | Instructions for maintaining docs and their sources. |
| ARCHITECTURE.md | Architecture overview: boundaries, components, flows, constraints, design sources. |
| Topic pages under docs/ | Explanations, architecture, reference contracts, guides, durable decisions. |
| Community policies and configuration entrypoints | Contribution, security, support, conduct, legal policies, configuration navigation. |
| Code, tests, configuration | Runtime behavior, executable expectations, configuration truth. |
| Drafts, specs, plans | Temporary proposals and work contracts with explicit approval state. |
| Skills, scripts, hooks | Reusable procedures and deterministic automation. |
| Vault notes | Knowledge in the narrowest established topic or PARA lane. |

Apply these owners at root and package/plugin boundaries. Link topic detail
instead of copying it into README or AGENTS.

1. Read the owner and verify claims against sources. Distinguish agreed intent
   from implemented behavior; chat and memory are leads.
2. For creation or structural refresh, load the matching reference and
   templates:

   | Destination | Reference |
   | ----------- | --------- |
   | Repository root or package entrypoints | [repository.md](references/targets/repository.md) |
   | Documentation index, instructions, or topic page | [documentation.md](references/targets/documentation.md) |
   | Vault root, lane, or note | [vault.md](references/targets/vault.md) |

   Focused updates use existing structure and the ownership table.
3. Reconcile the smallest coherent passage: merge overlap, remove superseded
   text, and preserve useful custom sections, valid constraints, and provenance.
   Create selected missing documents as needed. Explicit replacement applies
   only to named documents; identify useful or uncertain content it would
   discard and resolve ambiguous scope first. Detection, advice, and dry runs
   propose placements without writing. Edit the generator when it owns output.
4. Check affected facts, links, commands, examples, and generated output
   together.

## Output

Report changed owners and paths, reconciliation, verification, unresolved facts
or decisions, and material content discarded by explicit replacement. For
read-only requests, return proposed placements.

## Rules

- Stay within authorized scope. Propose moves beyond named editable files and
  retain content pending authorization.
- Templates supply structure, not facts. Keep applicable headings in template
  order and useful custom sections; remove authoring notes and unused optional
  sections. The standard architecture template retains all eight numbered
  sections.
- Follow explicit destinations and declared owners. New repository topics
  default to `docs/`; community policies default to repository root. Preserve
  configuration entrypoints such as `CONFIGURATION.md`, linking detailed
  explanations to their topic owner. Preserve vault organization unless
  migration or structural reset is requested.
- Use the owning engineering or tracking workflow for runtime, configuration, or
  work-record changes.
