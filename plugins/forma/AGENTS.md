# Forma Agents

## Overview

This portable Agent Plugins package owns code-design and refactoring guidance.
Shape owns both modes and the catalogue; Using introduces the plugin.

## Structure

- [`skills/`](skills/): instruction-driven skills:
  - [`shape/`](skills/shape/): design, assessment, refactoring, and references
  - [`using/`](skills/using/): plugin orientation
- [`plugin.json`](plugin.json): portable package identity
- [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json): Codex discovery and
  interface
- [`README.md`](README.md): human-facing package overview

## Tech Stack

- **Packaging**:
  [Agent Plugins v1.0.0](https://raw.githubusercontent.com/agentplugins/agent-plugins-spec/refs/heads/main/spec/1.0.0.md)
  in `plugin.json`; consult when changing portable metadata or package layout.
- **Instructions**: Markdown [Agent Skills](https://agentskills.io/llms.txt);
  use the agent index when changing skill format or resource-loading guidance.
- **Codex compatibility**:
  [Plugin format](https://developers.openai.com/plugins/build/plugins) in
  `.codex-plugin/plugin.json`; consult when changing skill discovery or
  interface metadata.

## Checks

Read changed skills with their references; check links, sources, and catalogue
coverage: 23 smells, 66 techniques, 22 patterns. Exercise affected decisions;
keep private evaluation fixtures outside this public package.

## Guardrails

- Keep behavior instruction-driven; client metadata only adapts discovery and
  interface.
- Keep entrypoints short and references inside their owning skill.
- Use unique `## Entry` headings with `### Problem` and `### Solution`; Markdown
  links target entries, not repeated subsection names.
- Write concise, original treatments with conditions, alternatives, exceptions,
  and individual source links.
- Shape owns assessment and refactoring boundaries; preserve its scope and
  behavior guarantees without adding a separate workflow.
