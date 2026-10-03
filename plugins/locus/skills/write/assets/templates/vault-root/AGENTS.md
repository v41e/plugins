# Vault Agents

## Overview

<!-- Vault-specific working boundary and constraints; do not repeat README explanations. -->

## Structure

<!-- Keep only actual agent-relevant lanes. These are defaults for a new or
explicitly reset PARA structure; each lane owns its children. -->

- [`00-inbox/`](00-inbox/): unclassified capture awaiting placement.
- [`10-projects/`](10-projects/): active efforts with defined outcomes.
- [`20-areas/`](20-areas/): ongoing responsibilities.
- [`30-resources/`](30-resources/): reusable references and distilled notes.
- [`40-archives/`](40-archives/): inactive material worth keeping.
- [`90-system/`](90-system/): templates and current organizational rules.
- [`README.md`](README.md): human entrypoint and placement policies.

## Guardrails

- Preserve valid meaning, sources, and established organization during refresh.
- Put unclassified capture in `00-inbox/` and structured notes in the narrowest
  matching PARA lane; follow the naming and placement policies in `README.md`.
- Use standard Markdown links in canonical entrypoints.
- Topic notes own explanations; lane entrypoints own local navigation and rules.
- Edit the owning template or source when it generates a note; check affected links.
