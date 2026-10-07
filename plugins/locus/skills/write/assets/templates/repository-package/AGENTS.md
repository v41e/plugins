# <!-- Package Or Plugin Name --> Agents

## Overview

<!-- Describe this package's responsibility and working boundary for agents in 1-3 sentences. Keep detailed constraints in Guardrails and the human entrypoint in README.md; link detailed explanations from docs/. -->

## Structure

<!-- Replace this example with verified local boundaries and canonical local docs. All repository-file links in this entrypoint stay within the package; inherit ancestor instructions without adding ancestor navigation. Verified external official references are permitted. Follow the local navigation contract in references/targets/repository.md.

- [`src/`](src/): main implementation
  - [`entrypoint.ts`](src/entrypoint.ts): primary entrypoint
- [`tests/`](tests/): package tests
- [`README.md`](README.md): human-facing package overview
-->

## Tech Stack

<!-- Optional. Retain dependency roles, relevant version/mode/target constraints, and verified official links with when to consult them. Include build/generation tooling when it affects edits; omit manifest inventories and unused categories. Follow the References guidance for source format. -->

- **Language/runtime**: <!-- e.g., TypeScript + Node 20, Python 3.13 -->
- **Framework**: <!-- e.g., FastAPI, Typer, CDK, React -->
- **Package manager**: <!-- e.g., pnpm, uv, poetry -->
- **Build/generation**: <!-- When relevant: orchestration tool or source generator and its owning configuration -->
- **Key dependencies**: <!-- e.g., aws-sdk, boto3, aws-lambda-powertools -->

## Setup & Build

<!-- Optional. List verified local install/build/run entrypoints, their purpose, and necessary setup or working directory. Preserve useful working setup; internal phases need not be separate commands. Use Commands for a non-code owner without a build. Remove inapplicable entries. -->

- Build: `<!-- primary command -->`
- Run: `<!-- local run command -->`

## Testing

<!-- Optional. List verified package-local tests/lint/typecheck and actual CI/task coverage, required extra fact/link/generator/output checks, and material side effects or limits. Follow root policy and affected behavior; add only package differences. Report interrupted/incomplete checks honestly. Use Checks when no test suite exists; remove unused entries. -->

- Focused test: `<!-- closest local test command -->`
- Full tests: `<!-- local suite command -->`
- Lint/typecheck: `<!-- applicable local command -->`

## Code Style

<!-- Optional. Inherit root/team conventions. Add only applicable verified language/framework references and local differences; repository-file links stay within this package. Preserve formatter/linter configuration and existing public docstring conventions. Do not repeat root guidance or create a generic design chapter. -->

## Code Review Rules

<!-- Optional. Omit this section unless verified package-specific review
priorities add to inherited review guidance and existing contracts, Guardrails,
and Testing/Checks. Link local owning compatibility or consumer rules rather than copying them. -->

## Guardrails

<!-- Keep only verified package-local constraints and permission boundaries. Distinguish actions permitted within those boundaries from actions requiring additional approval. -->

- <!-- Generated-vs-source boundary rule -->
- <!-- Important local side-effect rule -->
- <!-- Approval boundary or sensitive action rule -->

## References

<!-- Optional. Link useful package-local sources or verified external official references not already owned by Tech Stack or Code Style, with when to consult each. Prefer official Markdown or agent documentation; llms.txt aids discovery, and applicable official HTML is a fallback. Keep repository-file links inside this package; omit duplicates and empty sections. -->

- [<!-- Source -->](<!-- URL -->): <!-- When to consult it -->
