# Knowledge Map

A private knowledge map locates content outside the current repository. It is
optional: without one, Find can still search local sources. Map entries are
inventory leads; the selected destination owns current facts and instructions.

## Entrypoint Resolution

Find selects the first available entrypoint:

1. The user's explicit path.
2. `KNOWLEDGE_MAP_PATH`.
3. Repo-local `.knowledge-map/AGENTS.md`.
4. `~/.config/knowledge-map/AGENTS.md`.

An explicit path or environment value may name the map directory or its AGENTS
file. Start with the [generic example](../examples/knowledge-map/AGENTS.md),
keeping personal and company information outside this public package.

The [map adapter](../skills/find/references/platforms/knowledge-map.md) owns
resolution and retrieval semantics.
