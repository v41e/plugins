# Locus Agents

## Overview

This directory is the portable Agent Plugins v1 package root. Skills own shared
workflow behavior; client metadata only adapts package discovery.

## Structure

- [`examples/`](examples/): generic, publishable examples:
  - [`knowledge-map/`](examples/knowledge-map/): private knowledge-map starting point
- [`skills/`](skills/): shared instruction-driven workflows:
  - [`find/`](skills/find/): owned-knowledge and active-work discovery
  - [`init/`](skills/init/): knowledge-document creation, refresh, and templates
  - [`track/`](skills/track/): proportional Feature, Bug, and Task work tracking
  - [`distill/`](skills/distill/): durable-knowledge ownership and promotion
  - [`using/`](skills/using/): capability explanation and routing
- [`README.md`](README.md): human-facing plugin overview and quickstart

## Tech Stack

- **Packaging**: [Agent Plugins v1.0.0](https://raw.githubusercontent.com/agentplugins/agent-plugins-spec/refs/heads/main/spec/1.0.0.md)
  in `plugin.json`; consult when changing portable metadata or package layout.
- **Instructions**: Markdown [Agent Skills](https://agentskills.io/llms.txt);
  use the agent index when changing skill format or resource-loading guidance.
- **Codex compatibility**: [Plugin format](https://developers.openai.com/plugins/build/plugins)
  in `.codex-plugin/plugin.json`; consult when changing skill discovery or
  interface metadata.

## Commands

Run from this directory:

- Metadata syntax: `jq empty plugin.json .codex-plugin/plugin.json`.

## Verification

- For manifest changes, check both manifests' identity fields and discovery paths.
- For skill changes, read the entrypoint and affected references together; check
  routing, authorization, and completion boundaries.
- For template changes, compare the target reference, matching templates under
  `skills/init/assets/templates/`, and resulting document structure.

## Guardrails

- Keep shared behavior client-independent and instruction-driven.
- Keep client-specific metadata limited to discovery and interface adaptation.
- Treat map entries as discovery leads; selected destinations and their nearest
  instructions own current facts.
- Prefer short skill entrypoints with progressively loaded references.
- Add a deterministic runtime only when instructions cannot reliably perform the
  required operation.
- Keep examples and templates generic and safe to publish.
