# Repository Entrypoints

## Input

The selected root or package, its actual source layout, and existing entrypoints.

## Workflow

Use only the selected templates:

| Boundary | README | AGENTS | Architecture |
| -------- | ------ | ------ | ------------ |
| Root | [README](../assets/templates/repository-root/README.md) | [AGENTS](../assets/templates/repository-root/AGENTS.md) | [ARCHITECTURE](../assets/templates/repository-root/ARCHITECTURE.md) |
| Package or plugin | [README](../assets/templates/repository-package/README.md) | [AGENTS](../assets/templates/repository-package/AGENTS.md) | No package-level ARCHITECTURE.md |

Keep Overview to one or two short paragraphs. Structure maps relevant local
sources, important modules, source configuration, canonical docs, and direct child
boundaries with one-line responsibilities. Expand grouping directories only as
far as their direct owning packages; child entrypoints own their internals.
Use downward local paths: link the local README/AGENTS counterpart directly,
link child boundaries as directories, and leave ancestor navigation to the caller.

README supplies the shortest working start. AGENTS supplies editing instructions
and verified commands, checks, generated boundaries, and docs-to-read triggers.
Keep dependency constraints only when they affect an edit; link their owner.
Use [documentation.md](documentation.md) for displaced topic detail.
Keep Configuration as a link to its topic owner and References as edit-time
source links with a reason to consult each. `ARCHITECTURE.md` lives only at the
repository root. Create it when requested or when non-obvious system relationships
need an overview; retain its eight numbered sections, briefly marking inapplicable
sections where appropriate. Package-specific detail belongs in its declared docs
owner; do not create a package-level `ARCHITECTURE.md`.

## Output

Entrypoints that let humans and agents start work and find authoritative detail.

## Rules

- Keep useful manifests and generators in the map; omit caches and build output.
- Add local entrypoints only at meaningful independent boundaries.
- Link an owning Project under Work Tracking only when verified; describe stable
  conventions rather than current work status. Tracking mechanics belong to Track.
