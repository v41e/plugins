# Agents

## Overview

This repository is a public Agent Plugin marketplace. Keep root work focused on
repository-wide distribution and knowledge; keep plugin behavior inside its
owning directory under `plugins/`.

## Structure

- [`plugins/`](plugins/): installable plugin packages:
  - [`locus/`](plugins/locus/): Locus plugin; follow its local `AGENTS.md`
  - [`iter/`](plugins/iter/): Iter plugin; follow its local `AGENTS.md`
  - [`forma/`](plugins/forma/): Forma plugin; follow its local `AGENTS.md`
- [`.agents/plugins/marketplace.json`](.agents/plugins/marketplace.json):
  package discovery catalog
- [`release-please-config.json`](release-please-config.json) and
  [`.release-please-manifest.json`](.release-please-manifest.json): shared
  release configuration and version
- [`.github/workflows/`](.github/workflows/): repository checks and release
  automation
- [`.rumdl.toml`](.rumdl.toml): shared Markdown lint and formatting policy
- [`ARCHITECTURE.md`](ARCHITECTURE.md): consult before changing package formats,
  distribution, or cross-plugin integration boundaries
- [`CONTRIBUTING.md`](CONTRIBUTING.md): repository workflow and contribution
  requirements
- [`README.md`](README.md): human-facing repository overview

## Checks

Run `rumdl check .` from the repository root.

To format affected files, use `rumdl check --fix <paths>`, inspect the diff, and
rerun the check.

For metadata changes, verify catalog paths, matching manifest identities, and
the shared release version.

## Code Style

- Follow the [style guide](CONTRIBUTING.md#style-guide),
  [code standards](CONTRIBUTING.md#code-standards), and
  [review guidance](CONTRIBUTING.md#review).
- Skills, modes, workflows, and stages use `Purpose`, `Input`, `Workflow`,
  `Output`, and `Rules` in that order. Put routing inside the relevant section.
  Using skills are concise inventories: `Purpose`, `Skills`, and `Requirements`.
- Platform and integration references map concepts or conditions to concrete
  capabilities and their semantics; they do not define a second workflow.
  Conditional capability tables use `When`, `Capability`, and `Result`.

## Guardrails

- Keep private information, credentials, and personal knowledge maps out of this
  public repository.
- Treat marketplace and plugin distribution changes as supply-chain changes.
- Keep implementations and plugin-specific guidance inside the owning plugin.
- Preserve unrelated worktree changes.
- Do not release, publish, mutate external systems, or run destructive commands
  unless the user explicitly requests it.
