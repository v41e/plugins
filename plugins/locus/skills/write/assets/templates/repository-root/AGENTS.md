# Agents

## Overview

<!-- Describe this repository's purpose and working boundary for agents in 1-3 sentences. Keep detailed constraints in Guardrails, system design in ARCHITECTURE.md, and the human entrypoint in README.md; link detailed explanations from docs/. -->

## Structure

<!-- Replace this example with verified local boundaries and canonical local docs. Follow the local navigation contract in references/targets/repository.md. Route child work to its local AGENTS.md without expanding child internals here. Link existing CONTRIBUTING here for Git/contribution policy rather than duplicating it. Put useful source links and when to consult them beside their owning section; prefer verified official Markdown or agent documentation, with applicable official HTML as a fallback.

- [`packages/`](packages/): package grouping directory
  - [`package-name/`](packages/package-name/): direct package boundary; follow its local `AGENTS.md`
- [`plugins/`](plugins/): plugin grouping directory
  - [`plugin-name/`](plugins/plugin-name/): direct plugin boundary; follow its local `AGENTS.md`
- [`docs/`](docs/): canonical repository documentation
- [`ARCHITECTURE.md`](ARCHITECTURE.md): cross-component relationships; include only when this file exists
- [`README.md`](README.md): human-facing repository overview
-->

## Setup & Build

<!-- List verified install/build/run entrypoints, their purpose, and necessary setup or working directory. Preserve useful working setup; internal phases need not be separate commands. Remove inapplicable entries. For a non-code owner without a build, use Commands instead. -->

- Install: `<!-- install command -->`
- Build: `<!-- build command -->`
- Run: `<!-- run command -->`

## Testing

<!-- List verified focused/full tests, lint, and typecheck entrypoints as applicable. State actual CI/task coverage, required extra fact/link/generator/output checks, and material side effects or limits. Follow affected behavior and repository policy; report interrupted or incomplete checks honestly. Repeat checks after relevant changes or for diagnosis. Use Checks for a non-code owner without a test suite; do not invent one. -->

- Focused test: `<!-- closest test command -->`
- Full tests: `<!-- suite command -->`
- Lint/typecheck: `<!-- applicable command -->`

## Code Style

<!-- Optional. Team conventions live here or at their existing style owner; packages inherit them. Link only verified project-selected official guides and useful local overrides. Remove unused items and do not change tool configuration to imitate a guide. Keep longer contracts in their existing docs owner. -->

- <!-- Link existing formatter/linter configuration and applicable commands; automated formatting follows those tools. -->
- <!-- Link applicable language/framework conventions and useful local overrides, with when to consult them. -->
- <!-- Keep coherent statements/declarations and immediate error handling together; separate distinct logical blocks with blank lines, within formatter constraints. -->
- <!-- If adopted locally, use semantic NOTE/INFO for orientation, TODO/FIXME for follow-up, and WARNING for a real hazard. Use normal language comment syntax; avoid tagging every comment or restating obvious code. -->
- <!-- Link public docstring conventions for inputs, returns, errors, and material side effects. -->

## Code Review

<!-- Optional. Omit this section unless verified repository-specific review
priorities add to inherited review guidance and existing contracts, Guardrails,
and Testing/Checks. Link the owning rules rather than copying them. -->

## Work Tracking

<!-- Remove this section when no owning GitHub Project is verified. -->

- **Project:** [<!-- Project name -->](<!-- Project URL -->)
- **Milestones:** <!-- Remove when unused. Describe the stable naming or selection convention, not the current milestone. -->

## Guardrails

<!-- Record only verified repository constraints, permission boundaries, protected paths, generated-source rules, and external-system warnings that materially change agent behavior. Distinguish actions permitted within those boundaries from actions requiring additional approval. -->
