# Locus

Portable Agent Plugins v1 package for Locus knowledge lifecycle workflows.

## Overview

The package provides five client-independent Agent Skills for finding owned
context, maintaining canonical knowledge documents, tracking repository work,
distilling verified evidence, and choosing the smallest matching workflow.

> _Locus_ is Latin for "place": knowledge and active work belong with their
> verified owners, where they can be found, maintained, and trusted.

- **Type**: Agent Plugin.
- **Runtime**: compatible agent client; no bundled runtime or MCP server.

## Structure

- [`examples/`](examples/): generic, publishable examples:
  - [`knowledge-map/`](examples/knowledge-map/): private knowledge-map starting point
- [`skills/`](skills/): shared instruction-driven workflows:
  - [`find/`](skills/find/): owned-knowledge and active-work discovery
  - [`init/`](skills/init/): knowledge-document creation, refresh, and templates
  - [`track/`](skills/track/): proportional Feature, Bug, and Task lifecycle stages
  - [`distill/`](skills/distill/): durable-knowledge placement, promotion, and reconciliation
  - [`using/`](skills/using/): capability explanation and routing
- [`AGENTS.md`](AGENTS.md): plugin operating contract

## Quickstart

1. Install this package through a compatible client; in Codex, select `locus`
   from the `v41e` marketplace.
2. Reload plugins as required by the client; restart Codex desktop after local
   plugin changes.
3. Use `locus:using` when selection is unclear, or invoke `locus:find`,
   `locus:init`, `locus:track`, or `locus:distill` for the matching need.

## Configuration

A private knowledge map is optional; use it to locate knowledge outside the
current repository. Locus resolves its entrypoint in this order:

1. explicit path from the user.
2. `KNOWLEDGE_MAP_PATH`.
3. repo-local `.knowledge-map/AGENTS.md`.
4. `~/.config/knowledge-map/AGENTS.md`.

An explicit path or `KNOWLEDGE_MAP_PATH` may name the map directory or its
`AGENTS.md`. Without a map, Locus can still search the current repository.

Start with the [generic example](examples/knowledge-map/AGENTS.md), but keep
personal and company facts outside this package. The
[knowledge-map platform contract](skills/find/references/platforms/knowledge-map.md)
defines how Locus reads a map without treating inventory entries as current
facts.
