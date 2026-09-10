# Iter Agents

## Overview

This directory is the portable Agent Plugins v1 package root. Project-context
skills own shared behavior; `orchestrate` owns Codex-specific saved-project
dispatch, and client metadata adapts package discovery.

## Structure

- [`plugin.json`](plugin.json): portable Agent Plugins v1 identity metadata
- [`.codex-plugin/`](.codex-plugin/): Codex identity and interface metadata
- [`skills/`](skills/): shared instruction-driven workflows:
  - [`using/`](skills/using/): workflow selection and ownership routing
  - [`brief/`](skills/brief/): read-only status, plan, and retrospective modes
  - [`operate/`](skills/operate/): authorized engineering and documentation modes
  - [`orchestrate/`](skills/orchestrate/): Codex desktop coordination across saved projects
- [`README.md`](README.md): human-facing plugin overview and quickstart

## Tech Stack

- **Plugin**: Agent Plugins v1 with Codex compatibility metadata.
- **Agentic runtime**: Agent Skills with Git, GitHub CLI, repository context,
  and Codex desktop saved-project tools.

## Commands

- Metadata: `jq empty plugin.json .codex-plugin/plugin.json`.

## Verification

- For manifest changes, validate and inspect both metadata files.
- Validate each skill entrypoint and every referenced mode, platform, or
  integration mapping.
- Confirm each skill's relative reference links resolve inside that skill.
- Check local Markdown links and inspect the complete plugin diff.

## Guardrails

- Keep `brief` and `operate` inside the current task or owning execution context
  and client-independent.
- Keep client-specific metadata limited to discovery and interface adaptation.
- Keep references inside their owning skill.
- Keep `orchestrate` as the sole cross-project coordinator. It delegates to the
  exact owning saved Codex project one task at a time, preserves arbitrary
  caller work, and never edits a project repository from the umbrella workspace.
- Enter `orchestrate` only for an explicit request to dispatch, create, or
  continue project-owned tasks across an ordered saved-project list.
- When installed, Locus owns work-lifecycle and durable-knowledge workflows;
  Iter remains independently installable and does not depend on Locus.
- Keep briefs read-only and treat ideas or drafts as human triggers, not
  authorization to act.
- Local executors may not merge, release, deploy, create schedules, or modify live
  automations.
- Keep package content generic and safe to publish; preserve unrelated worktree
  changes.
