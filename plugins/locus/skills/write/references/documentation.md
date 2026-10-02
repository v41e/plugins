# Documentation

## Input

Subject, audience, verified sources, and the current documentation owner.

## Workflow

Prefer the existing topic passage and its structure. Keep a flat `docs/` layout
until distinct subjects need folders. Templates cover entrypoints and instructions:

| Document | Template | Owns |
| -------- | -------- | ---- |
| docs/README.md | [README](../assets/templates/documentation/README.md) | Subject navigation |
| docs/AGENTS.md | [AGENTS](../assets/templates/documentation/AGENTS.md) | Documentation maintenance instructions |

Use only sections the subject needs. The index and instructions link to topic
pages; they do not contain the topic explanation. Link package-local topics to
their existing root docs owner when that is the declared organization.
Independently distributed packages can own their own `docs/`; use the nearest
declared owner rather than creating duplicate pages at both levels. Repository
docs own cross-package subjects. Standard root `ARCHITECTURE.md` uses the
[repository reference](repository.md); other topic pages follow their subject
and existing local conventions without a prescribed topic template.

## Output

One authoritative passage per subject, discoverable from the relevant entrypoint.

## Rules

- Preserve intent, current behavior, and proposals as distinct states.
- Keep source references beside claims they establish. Verify version-sensitive
  claims against the actual configuration and current official documentation.
- Record generator ownership in docs instructions; edit the source, not its output.
