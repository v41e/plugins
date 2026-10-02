# Documentation

## Input

Subject, audience, verified sources, and the current documentation owner.

## Workflow

Prefer the existing topic passage. Keep a flat `docs/` layout until distinct
subjects need folders. For a new owner, select the smallest matching recipe:

| Document | Template | Owns |
| -------- | -------- | ---- |
| docs/README.md | [README](../assets/templates/documentation/README.md) | Subject navigation |
| docs/AGENTS.md | [AGENTS](../assets/templates/documentation/AGENTS.md) | Documentation maintenance instructions |
| Architecture | [architecture](../assets/templates/documentation/architecture.md) | Components, flows, consequential constraints |
| Concept | [concept](../assets/templates/documentation/concept.md) | Meaning, relationships, rationale |
| Reference | [reference](../assets/templates/documentation/reference.md) | Exact fields, defaults, behavior, constraints |
| Guide | [guide](../assets/templates/documentation/guide.md) | A verified task, prerequisites, actions, result |

Use only sections the subject needs. The index and instructions link to topic
pages; they do not contain the topic explanation. Link package-local topics to
their existing root docs owner when that is the declared organization.

## Output

One authoritative passage per subject, discoverable from the relevant entrypoint.

## Rules

- Preserve intent, current behavior, and proposals as distinct states.
- Keep source references beside claims they establish. Verify version-sensitive
  claims against the actual configuration and current official documentation.
- Record generator ownership in docs instructions; edit the source, not its output.
