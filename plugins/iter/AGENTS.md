# Iter Agents

## Overview

This portable Agent Plugins package owns briefs, tracking, maintenance loops,
and project dispatch. Keep host capabilities in adapters and engineering
methods in their owning skills.

## Structure

- [skills/](skills/): callable workflows; read the selected skill and its applicable references:
  - [brief/](skills/brief/): read-only status, plan, and retrospective
  - [track/](skills/track/): work contracts, approvals, and evidence gates
  - [maintain/](skills/maintain/): bounded engineering or documentation maintenance
  - [orchestrate/](skills/orchestrate/): authorized sequential project dispatch
  - [using/](skills/using/): skill selection
- [docs/](docs/): workflow documentation
- [README.md](README.md): human entrypoint
- [plugin.json](plugin.json): portable identity
- [.codex-plugin/plugin.json](.codex-plugin/plugin.json): Codex discovery and interface

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

- Check both manifests' identity fields, shared release version, and discovery paths.
- Read changed skills with affected references; check approvals, tracking,
  execution, discovery, and dispatch boundaries.
- Check affected links and representative decisions or artifacts. Keep private
  evaluation fixtures outside this public package.

## Guardrails

- Brief may discover and read across the requested scope; it never mutates or dispatches.
- Track owns records and gates. It never executes engineering work or delivers code.
- Maintain works in its authorized owner and selected checkout; it never
  dispatches, merges, releases, deploys, creates schedules, or changes live automations.
- Orchestrate alone creates or continues project-owned tasks, only with human
  authorization and exact assignment identity. It never edits child repositories
  from an umbrella context.
- Locus placement and Superpowers methods are optional integrations, not package
  dependencies or replacement workflows.
- Fold recurring generic review feedback into existing Iter guidance; keep
  domain and compatibility rules in their owning repository.
- Keep references, including harness mappings, inside their owning skill.
- Keep client metadata limited to discovery and interface adaptation. Live tool
  schemas own host arguments and response semantics.
- Keep package content generic; preserve unrelated worktree changes.
