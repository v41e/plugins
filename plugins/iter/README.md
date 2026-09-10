# Iter

Portable Agent Plugins v1 package for project-context engineering operations
and explicit sequential Codex saved-project orchestration.

## Overview

The package provides four Agent Skills: one router, two project-context
executors, and one Codex-specific cross-project coordinator.

> _Iter_ is Latin for "journey." The name also evokes iteration: understand,
> act, reassess, and repeat—a loop of deliberate progress.

- **Type**: Agent Plugin.
- **Local runtime**: current project context and its available local or remote
  evidence for `brief` and `operate`.
- **Orchestration runtime**: Codex desktop saved-project and task tools for
  `orchestrate`.

## Structure

- [`plugin.json`](plugin.json): portable Agent Plugins v1 identity metadata
- [`.codex-plugin/`](.codex-plugin/): Codex identity and interface metadata
- [`skills/`](skills/): shared instruction-driven workflows:
  - [`using/`](skills/using/): workflow selection and ownership routing
  - [`brief/`](skills/brief/): read-only status, plan, and retrospective modes
  - [`operate/`](skills/operate/): authorized engineering and documentation modes
  - [`orchestrate/`](skills/orchestrate/): explicit sequential dispatch across saved Codex projects
- [`AGENTS.md`](AGENTS.md): plugin operating contract

## Quickstart

1. Add this directory through a compatible client's plugin installation flow.
2. Start a new task so the client loads the skills.
3. Use `iter:using` when selection is unclear, or invoke `iter:brief`,
   `iter:operate`, or `iter:orchestrate` for the matching need.

Daily, weekly, and monthly describe a brief cadence, not separate modes.
