# Locus Agents

## Overview

This directory is the portable Agent Plugins v1 package root. Skills own shared
workflow behavior; client metadata only adapts package discovery.

## Structure

- [`skills/`](skills/): instruction-driven skills:
  - [`find/`](skills/find/): owned-knowledge and active-work discovery
  - [`write/`](skills/write/): content ownership, reconciliation, and templates
  - [`using/`](skills/using/): capability explanation and routing
- [`docs/`](docs/): configuration documentation
- [`examples/`](examples/): generic, publishable examples:
  - [`knowledge-map/`](examples/knowledge-map/): discovery-map starting point
- [`plugin.json`](plugin.json): portable package identity
- [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json): Codex discovery and
  interface
- [`README.md`](README.md): human-facing package overview

## Tech Stack

- **Packaging**:
  [Agent Plugins v1.0.0](https://raw.githubusercontent.com/agentplugins/agent-plugins-spec/refs/heads/main/spec/1.0.0.md)
  in `plugin.json`; consult when changing portable metadata or package layout.
- **Instructions**: Markdown [Agent Skills](https://agentskills.io/llms.txt);
  use the agent index when changing skill format or resource-loading guidance.
- **Codex compatibility**:
  [Plugin format](https://developers.openai.com/plugins/build/plugins) in
  `.codex-plugin/plugin.json`; consult when changing skill discovery or
  interface metadata.

## Checks

Read changed skills with their references; check routing, authorization, and
completion boundaries. For template changes, compare the target reference,
matching [templates](skills/write/assets/templates/), and resulting document
ownership and structure.

## Guardrails

- Keep shared behavior client-independent and instruction-driven.
- Keep client-specific metadata limited to discovery and interface adaptation.
- Treat map entries as discovery leads; selected destinations and their nearest
  instructions own current facts.
- Prefer short skill entrypoints with progressively loaded references.
- Add a deterministic runtime only when instructions cannot reliably perform the
  required operation.
- Keep examples and templates generic and safe to publish.
- README and AGENTS own entrypoints and instructions; topic docs own
  explanations.
- Locus owns content placement and structure; preserve the caller's writing
  style.
