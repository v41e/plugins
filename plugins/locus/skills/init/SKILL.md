---
name: init
description: Use when the user wants to create, refresh, align, migrate, or explicitly reset canonical README.md, AGENTS.md, or ARCHITECTURE.md knowledge documents.
---

# Init

Create, refresh, or explicitly reset canonical knowledge surfaces.

Templates are contracts for content and ownership, not replacement files. Real
project facts win. If a new target or template is needed, treat it as a plugin
change, not a runtime map lookup.

## Input

- The user's requested documents and operation.
- The selected destination, existing documents, and nearest `AGENTS.md`.

## Route

Select exactly one mode and one target. Read both selected references completely.

| Mode    | Use when                                                                        | Reference                                 |
| ------- | ------------------------------------------------------------------------------- | ----------------------------------------- |
| Create  | Every selected document is missing                                              | [create.md](references/modes/create.md)   |
| Refresh | Any selected document exists; includes non-destructive migration or alignment   | [refresh.md](references/modes/refresh.md) |
| Reset   | The user explicitly requests replacement and names the exact selected documents | [reset.md](references/modes/reset.md)     |

| Target                       | Use when                                             | Reference                                                         |
| ---------------------------- | ---------------------------------------------------- | ----------------------------------------------------------------- |
| Repository root              | The knowledge surface is repository-wide             | [repository-root.md](references/targets/repository-root.md)       |
| Repository package or plugin | The surface is local to a package or plugin boundary | [repository-package.md](references/targets/repository-package.md) |
| Obsidian root                | The knowledge surface is vault-wide                  | [obsidian-root.md](references/targets/obsidian-root.md)           |
| Obsidian lane                | The knowledge surface is local to a top-level lane   | [obsidian-lane.md](references/targets/obsidian-lane.md)           |

## Structure Contract

- `README.md` is human-facing; `AGENTS.md` is the concise semantic and
  procedural entrypoint. Give both a `Structure` section.
- `Structure` covers local boundaries and canonical local documentation.
- Describe only the current boundary and its immediate children. Repository
  roots route to direct packages or plugins; child documents own their internals.
- Prefer small README and AGENTS pairs at meaningful child boundaries. Keep a
  single root pair when the repository has no independent child boundary.
- In `Structure`, link child boundaries by directory and link the current
  boundary's README or AGENTS counterpart directly. Never link ancestors or a
  child's counterpart from this section.
- Expand grouping directories only to direct knowledge, package, or plugin
  boundaries.
- Omit administrative files, generated output, artifacts, caches, and lockfiles.

## Workflow

1. Identify the selected documents, mode, and target.
2. Read exactly that mode reference, target reference, selected templates, and
   existing selected documents completely.
3. Establish facts from current source, manifests, configuration, commands, and
   canonical docs. Verify new or changed dependency claims against official docs
   for the actual version and mode. Prefer available Markdown or agent-oriented
   pages; use `llms.txt` for discovery and official HTML when needed. Verify URLs.
   Templates own structure, not facts or wording; report evidence gaps and conflicts.
4. Apply the selected mode without changing unselected documents.
5. Replace retained placeholders with verified facts; remove authoring notes and
   unused optional sections. Report unresolved content instead of guessing.
6. Re-read related documents together and verify facts, links, commands, and
   ownership boundaries.

## Output

Return the mode, target, changed files, reconciliation summary, verification,
unresolved facts, and smallest useful follow-up.

## Rules

- Do not invent project, package, workflow, architecture, or command facts.
- Keep diffs minimal and focused.
- Preserve useful existing custom sections during Refresh. For repository
  `AGENTS.md`, add optional sections only when the corresponding need is verified:

  | Optional section          | Include when                                                                                   |
  | ------------------------- | ---------------------------------------------------------------------------------------------- |
  | Tech Stack                | Decision-relevant runtime, framework, or tooling choices lack an existing documentation owner. |
  | Local Setup               | Non-obvious agent setup is missing from the README.                                            |
  | Generated Files           | Source-to-output mappings need more than one Guardrails entry.                                 |
  | Compatibility & Contracts | API, schema, or platform constraints affect edits; link their specification.                   |
  | Troubleshooting           | Recurring failures have verified diagnosis or recovery steps.                                  |
  | Work Tracking             | An owning Project is verified under the repository-root target's conditions.                   |

  Preserve core section order; prefer an existing entry or owner link to repetition.

- Do not decide where long-lived knowledge should live; use `locus:distill` for
  placement decisions.
