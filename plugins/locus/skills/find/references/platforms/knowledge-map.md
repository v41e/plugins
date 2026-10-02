# Knowledge Map Adapter

## Capabilities

| When | Capability | Result |
| ---- | ---------- | ------ |
| A destination outside the repository is needed | Resolved map directory or its `AGENTS.md` | Destination inventories |
| An inventory matches the request | Smallest matching map entry | A candidate owner to verify |
| The owner is selected | Destination instructions and owned files | Current evidence for the answer |

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
