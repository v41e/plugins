# Iter

## Overview

Iter supports iteration: understand current work, maintain it, track evidence,
and coordinate authorized tasks. Engineering methods stay with the owning
project context and installed methods such as Superpowers.

## Structure

- [`skills/`](skills/): instruction-driven skills:
  - [`brief/`](skills/brief/): read-only status, plan, and retrospective
  - [`track/`](skills/track/): work contracts, approvals, and evidence gates
  - [`maintain/`](skills/maintain/): bounded engineering or documentation
    maintenance
  - [`orchestrate/`](skills/orchestrate/): authorized sequential project
    dispatch
  - [`using/`](skills/using/): skill selection
- [`docs/`](docs/): workflow boundaries and integration guidance
- [`plugin.json`](plugin.json): portable package identity
- [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json): Codex discovery and
  interface
- [`AGENTS.md`](AGENTS.md): package operating contract

## Quickstart

Install `iter` from the `v41e` marketplace in a compatible client and reload its
plugins. Invoke the matching skill; use `iter:using` when unsure.

Daily, weekly, and monthly are brief cadences, not separate skills.
