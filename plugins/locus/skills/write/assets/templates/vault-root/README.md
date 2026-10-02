# <!-- Vault Name -->

<!-- One-line description. -->

## Overview

<!-- Vault purpose, audience, and when to use it; keep topic explanations in notes. -->

## Structure

<!-- Numbered PARA defaults for new or explicitly reset structures. Preserve an
established organization unless migration is requested. List actual lanes;
each lane's entrypoints own its children. -->

- [`00-inbox/`](00-inbox/): capture, drafts, and unclassified material.
- [`10-projects/`](10-projects/): active efforts with defined outcomes and an end state.
- [`20-areas/`](20-areas/): ongoing responsibilities without a fixed end date.
- [`30-resources/`](30-resources/): reusable references organized by topic.
- [`40-archives/`](40-archives/): inactive material kept for future reference.
- [`90-system/`](90-system/): templates and current organizational rules.
- [`AGENTS.md`](AGENTS.md): vault operating instructions.

## Policies

### Naming & Placement

<!-- Preserve existing conventions on refresh. These defaults apply to new or
explicitly reset structures. -->

- Top-level lanes use `NN-kebab-case`; subfolders use `kebab-case`.
- Notes use `kebab-case.md`; prefer nested folders over mixed name separators.
- Put unclassified capture in `00-inbox/`; place structured notes directly in the
  narrowest matching PARA lane.
- Keep each note focused on one topic or responsibility; archive inactive material.

### Links & References

- Use standard Markdown links in canonical entrypoints: `[label](path/to/file.md)`.
- Link directly to the topic owner and retain sources beside the claims they support.

### PARA

<!-- The lane map defines Projects, Areas, Resources, and Archives. Record only
additional local placement decisions here. -->

- [PARA](https://fortelabs.com/blog/para/): organizing work and reusable knowledge.
