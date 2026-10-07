# Repository Entrypoints

## Purpose

Give humans and agents a short working start and clear links to authoritative detail.

## Input

The selected root or package, its actual source layout, and existing entrypoints.

## Workflow

| Boundary | README | AGENTS | Architecture |
| -------- | ------ | ------ | ------------ |
| Root | [README](../../assets/templates/repository-root/README.md) | [AGENTS](../../assets/templates/repository-root/AGENTS.md) | [ARCHITECTURE](../../assets/templates/repository-root/ARCHITECTURE.md) |
| Package or plugin | [README](../../assets/templates/repository-package/README.md) | [AGENTS](../../assets/templates/repository-package/AGENTS.md) | No package-level ARCHITECTURE.md |

1. **README.md:** give humans the shortest working start. Keep Overview to one or
   two paragraphs and Configuration as a link to its topic owner.
2. **AGENTS.md:** give agents editing boundaries, verified commands and checks,
   generator ownership, and reasons to consult authoritative references. Include
   dependency constraints only when they affect an edit; link their owner.
   Use Setup & Build for install/build/run entrypoints and Testing for focused/full
   tests, lint, typecheck, required extra checks, and honest coverage or side-effect
   limits. Follow affected behavior and repository policy, not a blanket full-suite
   rule. For non-code owners without build/test suites, replace those headings with
   applicable Commands/Checks; do not invent commands or leave empty sections.
   Team conventions live once at the root or their existing style owner. Optional
   compact Code Style may link verified project-selected official guides and useful
   local overrides: existing formatter/linter configuration, coherent logical
   spacing, selective semantic comment prefixes, and public docstring conventions.
   Packages inherit root policy and add only relevant language/framework references
   or differences. Do not impose a guide, editor, tag taxonomy, or new style skill.
   Include Code Review Rules only when verified, scoped review priorities add
   value beyond inherited guidance, existing contracts, Guardrails, and Testing/Checks.
   Link the owning rules rather than copying them; otherwise omit the section.
3. **Structure in both:** map relevant local sources, important modules, source
   configuration, canonical docs, and direct child boundaries with one-line
   responsibilities. Expand grouping directories only to direct owning packages;
   child entrypoints own their internals. Link local README/AGENTS counterparts
   directly and child boundaries as directories; leave ancestor navigation to the
   caller. All repository-file links in package entrypoints stay within the package;
   verified external official references are permitted. Preserve useful working
   setup, module/configuration maps, and generator ownership. Route Git workflow to
   existing CONTRIBUTING from the root rather than repeating it. Use
   [documentation.md](documentation.md) for displaced topic detail.
4. **ARCHITECTURE.md:** create only at repository root when requested or when
   non-obvious system relationships need an overview. Retain its eight numbered
   sections, briefly marking inapplicable sections. Package-specific detail belongs
   in its declared docs owner; do not create a package-level ARCHITECTURE.md.

## Output

Entrypoints that let humans and agents start work and find authoritative detail.

## Rules

- Keep useful manifests and generators in the map; omit caches and build output.
- Add local entrypoints only at meaningful independent boundaries.
- Link an owning Project under Work Tracking only when verified; describe stable
  conventions rather than current work status. Tracking mechanics belong to Track.
