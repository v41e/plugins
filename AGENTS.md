# Agents

## Overview

This repository is a public Agent Plugin marketplace. Keep root work focused on
repository-wide distribution and knowledge; keep plugin behavior inside its
owning directory under `plugins/`.

## Structure

- [`plugins/`](plugins/): installable plugin packages:
  - [`locus/`](plugins/locus/): Locus plugin; follow its local `AGENTS.md`
  - [`iter/`](plugins/iter/): Iter plugin; follow its local `AGENTS.md`
- [`ARCHITECTURE.md`](ARCHITECTURE.md): system relationships and boundaries
- [`README.md`](README.md): human-facing repository overview

## Commands

- Metadata: `jq empty .agents/plugins/marketplace.json .release-please-manifest.json release-please-config.json plugins/locus/plugin.json plugins/locus/.codex-plugin/plugin.json plugins/iter/plugin.json plugins/iter/.codex-plugin/plugin.json`.
- Plugin checks belong to the owning directory under `plugins/`.

## Verification

- Validate repository and plugin JSON with the metadata command.
- Confirm catalog paths exist and the README plugin table matches the catalog.
- Keep matching manifest fields and ordering aligned across plugins; homepages
  point to each package, while repository URLs identify the shared repository.
- Follow the owning plugin's `AGENTS.md` for plugin-level verification.

## Guardrails

- Keep private information, credentials, and personal knowledge maps out of
  this public repository.
- Treat marketplace and plugin distribution changes as supply-chain changes.
- Keep implementations and plugin-specific guidance inside the owning plugin.
- Skills, modes, workflows, and phases use `Input`, `Workflow`, `Output`, and
  `Rules` in that order. Add routing sections only where needed.
- Platform and integration references map concepts or conditions to concrete
  capabilities and their semantics; they do not define a second workflow.
- Keep the marketplace catalog and root plugin table aligned.
- Preserve unrelated worktree changes.
- Do not release, publish, mutate external systems, or run destructive commands
  unless the user explicitly requests it.
