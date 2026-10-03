# Documentation

## Purpose

Keep topic knowledge in one authoritative owner with usable navigation and maintenance rules.

## Input

Subject, audience, verified sources, and the current documentation owner.

## Workflow

| Document | Template |
| -------- | -------- |
| docs/README.md | [README](../../assets/templates/documentation/README.md) |
| docs/AGENTS.md | [AGENTS](../../assets/templates/documentation/AGENTS.md) |

1. **docs/README.md:** state documentation scope and route readers to existing
   subjects with one-line responsibilities. Identify an authoritative source or
   generated reference when readers need it; keep explanations in topic pages.
2. **docs/AGENTS.md:** map claims to code, tests, configuration, approved decisions,
   and generators. State maintenance boundaries and the checks needed for changes
   to facts, links, commands, or examples; keep topic explanations in their owners.
   Include Code Review Rules only when verified, scoped review priorities add
   value beyond inherited guidance and existing contracts, Sources, Guardrails, and
   Verification. Link the owning rules rather than copying them; otherwise omit
   the section. Keep intended, implemented, and verified live state distinct.
3. **Topic pages:** integrate evidence in the nearest existing passage using its
   structure. Keep `docs/` flat until distinct subjects need folders. Follow the
   declared organization: repository docs own cross-package subjects; independently
   distributed packages can own local `docs/`. Link to existing owners instead of
   duplicating pages. Standard root `ARCHITECTURE.md` uses the
   [repository reference](repository.md); other topics have no prescribed template.

## Output

One authoritative passage per subject, discoverable from the relevant entrypoint.

## Rules

- Preserve intent, current behavior, and proposals as distinct states.
- Keep source references beside claims they establish. Verify version-sensitive
  claims against actual configuration and current official documentation.
- Edit a generator's source and check its output together.
