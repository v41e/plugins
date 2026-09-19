# Iter Agents

## Overview

This directory is the portable Agent Plugins v1 package root. Project-context
skills own shared behavior; `orchestrate` owns Codex-specific saved-project
dispatch, and client metadata adapts package discovery.

## Structure

- [`skills/`](skills/): shared instruction-driven workflows:
  - [`using/`](skills/using/): workflow selection and ownership routing
  - [`brief/`](skills/brief/): read-only status, plan, and retrospective modes
  - [`operate/`](skills/operate/): authorized engineering and documentation modes
  - [`orchestrate/`](skills/orchestrate/): Codex desktop coordination across saved projects
- [`README.md`](README.md): human-facing plugin overview and quickstart

## Tech Stack

- **Packaging**: [Agent Plugins v1.0.0](https://raw.githubusercontent.com/agentplugins/agent-plugins-spec/refs/heads/main/spec/1.0.0.md)
  in `plugin.json`; consult when changing portable metadata or package layout.
- **Instructions**: Markdown [Agent Skills](https://agentskills.io/llms.txt);
  use the agent index when changing skill format or resource-loading guidance.
- **Codex compatibility**: [Plugin format](https://developers.openai.com/plugins/build/plugins)
  in `.codex-plugin/plugin.json`; consult when changing skill discovery or
  interface metadata.
- **Execution tools**: the host supplies Git and GitHub access when required.
  `orchestrate` requires Codex desktop saved-project tools; use live tool
  schemas with its [Codex adapter](skills/orchestrate/references/platforms/codex.md).

## Commands

Run from this directory:

- Metadata syntax: `jq empty plugin.json .codex-plugin/plugin.json`.

## Verification

- For manifest changes, check both manifests' identity fields and discovery paths.
- For skill changes, read the entrypoint and affected references together; check
  brief, execution, and dispatch boundaries. Reference links stay inside their
  owning skill.

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
- Local `operate` runs may not merge, release, deploy, create schedules, or modify
  live automations.
- Keep package content generic and safe to publish; preserve unrelated worktree
  changes.
