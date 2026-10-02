# Documentation Agents

## Scope

<!-- Subjects owned here and links to neighboring owners. Keep instructions local. -->

## Sources

<!-- Map each documented contract to its actual source: code, tests, configuration,
approved decisions, or a specification. Name any generator and its editable input. -->

## Verification

<!-- State required checks for changed claims, links, commands, examples, and
version-sensitive references. Include generator checks only when they apply. -->

## Code Review Rules

Inherit shared review guidance; add only verified documentation-specific rules.

- Check changed claims, commands, and examples against their owning sources and
  stated environment; distinguish intended, implemented, and verified live state.
- Flag consequential drift or conflicting ownership. Keep README navigation
  useful and detailed guides with their declared owner.

## Guardrails

- Integrate changes in the existing topic passage; README owns navigation.
- Preserve approved intent, implemented behavior, and proposals as distinct states.
- Edit generated documentation through its source and inspect affected output.
- Reconcile overlapping or superseded guidance while preserving valid constraints
  and source references.
<!-- Add verified local maintenance boundaries; avoid repeating inherited rules. -->
