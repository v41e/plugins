# Agents

## Overview

This repository is a public Agent Plugin marketplace. Keep root work focused on
repository-wide distribution and knowledge; keep plugin behavior inside its
owning directory under `plugins/`.

## Structure

- [`plugins/`](plugins/): installable plugin packages:
  - [`locus/`](plugins/locus/): Locus plugin; follow its local `AGENTS.md`
  - [`iter/`](plugins/iter/): Iter plugin; follow its local `AGENTS.md`
- [`ARCHITECTURE.md`](ARCHITECTURE.md): consult before changing package formats,
  distribution, or cross-plugin integration boundaries
- [`CONTRIBUTING.md`](CONTRIBUTING.md): repository workflow and contribution requirements
- [`README.md`](README.md): human-facing repository overview

## Commands

- Metadata: `jq empty .agents/plugins/marketplace.json .release-please-manifest.json release-please-config.json plugins/locus/plugin.json plugins/locus/.codex-plugin/plugin.json plugins/iter/plugin.json plugins/iter/.codex-plugin/plugin.json`.

## Verification

- CI checks JSON syntax and whitespace; it does not validate schemas or skill
  behavior. There is no compiled build or runtime test suite.
- For metadata changes, check catalog paths, README entries, shared manifest
  fields/order and release version. Homepages identify packages; repository URLs
  identify the shared repository.
- For docs, check affected links and facts; follow the owning plugin's `AGENTS.md`
  for skill and template checks.

## Guardrails

- Keep private information, credentials, and personal knowledge maps out of
  this public repository.
- Treat marketplace and plugin distribution changes as supply-chain changes.
- Keep implementations and plugin-specific guidance inside the owning plugin.
- Skills, modes, workflows, and stages use `Input`, `Workflow`, `Output`, and
  `Rules` in that order. Add routing sections only where needed.
- Platform and integration references map concepts or conditions to concrete
  capabilities and their semantics; they do not define a second workflow.
- Preserve unrelated worktree changes.
- Do not release, publish, mutate external systems, or run destructive commands
  unless the user explicitly requests it.
