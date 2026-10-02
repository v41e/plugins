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
   Populate Code Review Rules from verified contracts and checks; packages inherit
   shared guidance and add actual compatibility boundaries and consumers.
3. **Structure in both:** map relevant local sources, important modules, source
   configuration, canonical docs, and direct child boundaries with one-line
   responsibilities. Expand grouping directories only to direct owning packages;
   child entrypoints own their internals. Link local README/AGENTS counterparts
   directly and child boundaries as directories; leave ancestor navigation to the
   caller. Use [documentation.md](documentation.md) for displaced topic detail.
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
