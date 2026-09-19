# Agents

## Overview

<!-- Describe this repository's purpose and working boundary for agents in 1-3 sentences. Keep detailed constraints in Guardrails, system design in ARCHITECTURE.md, and human-facing explanation in README.md. -->

## Structure

<!-- Replace this example with verified local boundaries and canonical local docs. Follow the structure contract in SKILL.md. Route child work to its local AGENTS.md without expanding child internals here.

- [`packages/`](packages/): package grouping directory
  - [`package-name/`](packages/package-name/): direct package boundary; follow its local `AGENTS.md`
- [`plugins/`](plugins/): plugin grouping directory
  - [`plugin-name/`](plugins/plugin-name/): direct plugin boundary; follow its local `AGENTS.md`
- [`docs/`](docs/): canonical repository documentation
- [`ARCHITECTURE.md`](ARCHITECTURE.md): cross-component relationships; include only when this file exists
- [`README.md`](README.md): human-facing repository overview
-->

## Commands

<!-- List verified entrypoints, their purpose, and necessary setup or working directory. Keep useful focused checks; internal build phases need not be separate commands. Remove inapplicable examples. -->

- Install: `<!-- install command -->`
- Build: `<!-- build command -->`
- Test: `<!-- test command -->`

## Verification

<!-- Briefly state build coverage from task definitions and CI, required extra checks, and material side effects or limits. Repeat covered checks only after relevant changes or for diagnosis. Document project policy, not historical pass claims. -->

## Work Tracking

<!-- Remove this section when no owning GitHub Project is verified. -->

- **Project:** [<!-- Project name -->](<!-- Project URL -->)
- **Milestones:** <!-- Remove when unused. Describe the stable naming or selection convention, not the current milestone. -->

## Guardrails

<!-- Record only verified repository constraints, permission boundaries, protected paths, generated-source rules, and external-system warnings that materially change agent behavior. Distinguish actions permitted within those boundaries from actions requiring additional approval. -->

## References

<!-- Optional. Link useful sources not already owned by Tech Stack or architecture, with when to consult each. Prefer verified official Markdown or agent documentation; llms.txt aids discovery, and applicable official HTML is a fallback. Omit duplicates and empty sections. -->

- [<!-- Source -->](<!-- URL -->): <!-- When to consult it -->
