# Local Artifact Metadata

Use YAML front matter for local draft/spec/plan metadata. Follow an existing
repository schema; otherwise use these defaults. This formatting contract adds
no artifacts or approval gates to the selected workflow. Keep substantive
content in Markdown and review metadata in the caller's report template.

## Field Owners

| Artifact | Fields |
| -------- | ------ |
| Draft | `kind`, `work_type`; optional `stage`, `issue_url`, `backlog_url`, `priority`, `effort`, `start_date`, `target_date`, `sync` |
| Spec | `kind`, plus `draft` or `issue_url` |
| Plan | `kind`, plus `spec`; otherwise `draft` or `issue_url` |

An existing Issue owns the work contract; no local draft is required. When a
local draft exists, it owns local work-level metadata and mirrors agreed fields
under the synchronization contract. Specs and plans link their predecessor
instead of copying scheduling metadata. `stage` uses the selected workflow's
stage names; remote status mappings remain platform-specific.

Use raw strings for links, not Markdown or wiki-link syntax. Local paths are
repository-root-relative; identify the owning repository for cross-repository
references. Keep the human title in the Markdown heading, not a duplicate field.

## Examples

These headers precede the artifact's existing body; they do not replace its
content structure. Null values below mean confirmed unset values.

### Draft

```yaml
---
kind: "draft"
work_type: "task"
stage: "scope"
issue_url: null
priority: null
effort: null
---
```

Use `feature`, `bug`, or `task` for `work_type`. Add dates only when known:
`start_date` records actual execution start; `target_date` records a real
commitment. Use the caller's priority/effort scales; never invent a mapping.

### Spec

```yaml
---
kind: "spec"
draft: "docs/superpowers/drafts/example.md"
---
```

### Plan

```yaml
---
kind: "plan"
spec: "docs/superpowers/specs/example.md"
---
```

When no spec exists, link the draft instead. If work began from an Issue without
an earlier local artifact, use `issue_url: "https://example.com/work/123"` in
the spec or plan. Link the existing predecessor; do not create one to fill
metadata.

## Synchronization Baseline

If local metadata owns the last confirmed remote values, keep only mirrored
fields in an optional baseline:

```yaml
sync:
  record_url: "https://example.com/work/123"
  baseline:
    priority: null
    effort: null
```

This example means both fields were verified empty on that record. An absent
baseline is unknown. Preserve pending/conflicting edits; update the baseline
only after verified agreement. A different remote record needs its own baseline.
Do not add a redundant `synced` flag or copy this baseline into specs and plans.

## Rules

- Quote strings, including dates, timestamps, identifiers, URLs and hashes. Use
  `YYYY-MM-DD` for dates and ISO-8601 with an offset for timestamps.
- Omit unknown or inapplicable fields; use `null` only for a known empty value.
  Empty values and missing evidence are different; explain material uncertainty
  in the body. Preserve unrelated fields in an existing schema.
- Stage, status, URLs and verdicts describe recorded state; none grants
  approval. Keep decisions, authorization evidence and verification reasoning in
  their existing owners. Place a reviewed artifact's hash in its separate review
  report, not inside the artifact itself.
- Follow the platform adapter when publishing snapshots. Local tracking headers
  and synchronization baselines do not belong in Issue bodies or comments;
  preserve the approved substantive content and mapped remote fields.
- Apply this format to new or deliberately refreshed artifacts. Do not rewrite
  existing artifacts or immutable review reports solely to migrate metadata.
