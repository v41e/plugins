# Documentation

## Purpose

Keep topic knowledge in one authoritative owner with usable navigation and maintenance rules.

## Input

Subject, audience, verified sources, and the current documentation owner.

## Workflow

| Document | Template |
| -------- | -------- |
| docs/README.md | [README](../../assets/templates/documentation/README.md) |
| docs/AGENTS.md | [AGENTS](../../assets/templates/documentation/AGENTS.md) |

1. **docs/README.md:** use Overview for scope/audience and Structure for existing
   topic owners with one-line responsibilities. Add a short Quickstart only when
   orientation benefits. Keep meaningful source or generated-reference pointers
   beside their owning passage; no routine Subjects/Sources inventories are required.
2. **docs/AGENTS.md:** use Overview and Structure, applicable Commands/Checks, and
   Guardrails. Verify claims against code, tests, configuration, approved decisions,
   and generators; identify non-obvious editable inputs when useful without a
   mandatory Sources inventory. Check changed facts, links, commands, examples,
   and relevant output; keep topic explanations in their owners. Optional Code
   Style inherits team conventions and adds only verified documentation/example
   differences; preserve formatter/linter and public docstring ownership.
   Include Code Review only when verified, scoped review priorities add
   value beyond inherited guidance, existing contracts, Guardrails, and Checks.
   Link the owning rules rather than copying them; otherwise omit
   the section. Keep intended, implemented, and verified live state distinct.
3. **Topic pages:** integrate evidence in the nearest existing passage using its
   structure. Keep `docs/` flat until distinct subjects need folders. Follow the
   declared organization: repository docs own cross-package subjects; independently
   distributed packages can own local `docs/`. Link to existing owners instead of
   duplicating pages. Standard root `ARCHITECTURE.md` uses the
   [repository reference](repository.md); other topics have no prescribed template.

## Output

One authoritative passage per subject, discoverable from the relevant entrypoint.

## Rules

- Preserve intent, current behavior, and proposals as distinct states.
- Keep source references beside claims they establish. Verify version-sensitive
  claims against actual configuration and current official documentation.
- Edit a generator's source and check its output together.
