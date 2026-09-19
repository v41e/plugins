# <!-- Package Or Plugin Name --> Agents

## Overview

<!-- Describe this package's responsibility and working boundary for agents in 1-3 sentences. Keep detailed constraints in Guardrails and human-facing explanation in README.md. -->

## Structure

<!-- Replace this example with verified local boundaries and canonical local docs. Follow the structure contract in SKILL.md.

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

## Commands

<!-- Optional. List verified entrypoints, their purpose, and necessary setup or working directory. Keep useful focused checks; internal build phases need not be separate commands. -->

- Build: `<!-- primary command -->`
- Test: `<!-- package-local test command -->`

## Verification

<!-- Briefly state build coverage from task definitions and CI, required extra checks, and material side effects or limits. Repeat covered checks only after relevant changes or for diagnosis. Add only package-specific guidance beyond the root policy. -->

## Guardrails

<!-- Keep only verified package-local constraints and permission boundaries. Distinguish actions permitted within those boundaries from actions requiring additional approval. -->

- <!-- Generated-vs-source boundary rule -->
- <!-- Important local side-effect rule -->
- <!-- Approval boundary or sensitive action rule -->

## References

<!-- Optional. Link useful sources not already owned by Tech Stack or architecture, with when to consult each. Prefer verified official Markdown or agent documentation; llms.txt aids discovery, and applicable official HTML is a fallback. Omit duplicates and empty sections. -->

- [<!-- Source -->](<!-- URL -->): <!-- When to consult it -->
