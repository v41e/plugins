# Vaults

## Purpose

Place knowledge in a navigable Markdown vault with explicit PARA boundaries.

## Input

The selected Markdown knowledge base, vault, lane, or note and its current organization.

## Workflow

| Entrypoint | README | AGENTS |
| ---------- | ------ | ------ |
| Root | [README](../../assets/templates/vault-root/README.md) | [AGENTS](../../assets/templates/vault-root/AGENTS.md) |
| Lane | [README](../../assets/templates/vault-lane/README.md) | [AGENTS](../../assets/templates/vault-lane/AGENTS.md) |

1. **Root README.md:** state vault purpose, actual top-level lanes, naming and
   placement rules. For a new or explicitly reset structure, use the numbered PARA
   defaults below. Preserve an established organization unless migration is requested.
2. **Root AGENTS.md:** map agent-relevant lanes and record placement, source, and
   editing boundaries. Link to README policies instead of repeating explanations.
3. **Lane README.md:** use a semantic title such as Inbox or Resources. State its
   purpose, real immediate children, and what belongs here or in neighboring lanes.
4. **Lane AGENTS.md:** give additive lane-specific placement and maintenance rules;
   map real children and route unclassified material to the established inbox.
5. **Notes:** integrate verified knowledge in the narrowest topic owner. Already
   structured notes go directly to the matching lane; unclassified capture goes
   to the inbox. Topic notes own durable explanations.

| Default lane | Content |
| ------------ | ------- |
| 00-inbox/ | Capture, drafts, and unclassified material awaiting placement. |
| 10-projects/ | Active efforts with defined outcomes and an end state. |
| 20-areas/ | Ongoing responsibilities without a fixed end date. |
| 30-resources/ | Reusable reference material organized by topic. |
| 40-archives/ | Inactive material retained for future reference. |
| 90-system/ | Templates and current organizational rules. |

## Output

Verified knowledge integrated in its topic owner with usable root and lane navigation.

## Rules

- Creating entrypoints does not authorize reorganizing an existing vault.
- New PARA structures use `NN-kebab-case` top-level lanes, `kebab-case` subfolders,
  and `kebab-case.md` notes; prefer nested folders over mixed name separators.
- Use standard Markdown links in canonical entrypoints so filesystem-based agents
  can resolve targets. Preserve existing note links and formats during refresh.
