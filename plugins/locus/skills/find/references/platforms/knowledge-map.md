# Knowledge Map Adapter

Use the knowledge map only to discover a destination outside the current
repository.

## Concept mapping

| Concept               | Concrete surface                          | Semantics                                       |
| --------------------- | ----------------------------------------- | ----------------------------------------------- |
| Discovery entrypoint  | Resolved map directory or its `AGENTS.md` | Locates destination inventories                 |
| Destination inventory | Smallest matching map entry               | Identifies a candidate owner, not current facts |
| Verified knowledge    | Destination instructions and owned files  | Supplies evidence for the answer                |

## Entrypoint resolution

Resolve its entrypoint in this order:

1. explicit path from the user.
2. `KNOWLEDGE_MAP_PATH`.
3. repo-local `.knowledge-map/AGENTS.md`.
4. `~/.config/knowledge-map/AGENTS.md`.

An explicit value may name the directory or its `AGENTS.md`. Read the entrypoint
and only the smallest matching destination inventory. The map owns destination
inventory; the selected destination and its nearest instructions own facts.
Before answering a factual question, read that destination's nearest
`AGENTS.md` and only the relevant owned surface.

## Boundary semantics

If no map exists, continue locally when possible. Report the missing map only
when broader discovery is required, and never invent a destination.
