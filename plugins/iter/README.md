# Iter

Portable Agent Plugins v1 package for bounded project-context operations and
explicit sequential Codex saved-project orchestration.

## Overview

The package provides a router, read-only briefs, work tracking, a bounded
operator, and a cross-project coordinator.

> _Iter_ is Latin for "journey." The name also evokes iteration: understand,
> act, reassess, and repeat—a loop of deliberate progress.

- **Type**: Agent Plugin.
- **Local runtime**: `operate` advances authorized work in the current project.
  It manages the run; Track records contracts, approvals, and evidence gates.
  The owning project context supplies engineering methods.
- **Orchestration runtime**: Codex desktop saved-project and task tools for
  `orchestrate`.

## Structure

- [`skills/`](skills/): shared instruction-driven workflows:
  - [`using/`](skills/using/): workflow selection and ownership routing
  - [`brief/`](skills/brief/): read-only status, plan, and retrospective modes
  - [`track/`](skills/track/): work records, approvals, and evidence gates
  - [`operate/`](skills/operate/): one bounded authorized engineering or documentation run
  - [`orchestrate/`](skills/orchestrate/): explicit sequential dispatch across saved Codex projects
- [`AGENTS.md`](AGENTS.md): plugin operating contract

## Quickstart

1. Install this package through a compatible client; in Codex, select `iter`
   from the `v41e` marketplace.
2. Reload plugins as required by the client; restart Codex desktop after local
   plugin changes.
3. Use `iter:using` when selection is unclear, or invoke `iter:brief`,
   `iter:track`, `iter:operate`, or `iter:orchestrate` for the matching need.

Daily, weekly, and monthly describe a brief cadence, not separate modes.
