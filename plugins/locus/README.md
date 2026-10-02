# Locus

## Overview

Find authoritative content and put verified knowledge in its proper owner.
Locus means place: entrypoints help humans and agents start work; topic docs own
explanations and reference material. Writing style remains the caller's choice.

## Structure

- [skills/](skills/): portable instruction-driven skills:
  - [find/](skills/find/): read-only ownership and evidence discovery
  - [write/](skills/write/): content placement, reconciliation, and templates
  - [track/](skills/track/): repository work tracking
  - [using/](skills/using/): skill selection
- [docs/](docs/): configuration documentation
- [examples/knowledge-map/](examples/knowledge-map/): generic discovery-map example
- [plugin.json](plugin.json): portable package identity
- [.codex-plugin/plugin.json](.codex-plugin/plugin.json): Codex discovery and interface
- [AGENTS.md](AGENTS.md): working instructions

## Quickstart

Install `locus` from the `v41e` marketplace in a compatible client and reload its
plugins. Invoke `locus:find` or `locus:write`; use `locus:using` when unsure.
Optional cross-destination discovery uses a [knowledge map](docs/knowledge-map.md).
