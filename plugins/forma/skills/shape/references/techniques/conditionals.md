# Simplifying Conditional Expressions

## Consolidate Conditional Expression

[Source](https://refactoring.guru/consolidate-conditional-expression)

### Problem

Separate checks express one decision with the same outcome.

### Solution

- All checks must pass → combine with `and`; any check is enough → combine with
  `or`. Preserve check order, side effects, and skipped checks.
- Combined expression hides intent →
  [Extract Method](composing-methods.md#extract-method) with a decision name.

## Consolidate Duplicate Conditional Fragments

[Source](https://refactoring.guru/consolidate-duplicate-conditional-fragments)

### Problem

Every branch repeats the same work.

### Solution

- Common beginning/end → move before/after the conditional only when it still
  selects the same branch and preserves effect order, execution count, and
  failures.
- Common work inside branches → move to an edge only when dependencies permit.
- Substantial common operation →
  [Extract Method](composing-methods.md#extract-method).

## Decompose Conditional

[Source](https://refactoring.guru/decompose-conditional)

### Problem

Conditions and branch bodies conceal the decision and its outcomes.

### Solution

- Unclear check → [Extract Method](composing-methods.md#extract-method) named
  for the decision; a short expression can still benefit.
- Complex `then`/`else` bodies → extract each meaningful outcome separately.
- Keep evaluation order, short circuit behavior, and branch effects unchanged.

## Replace Conditional with Polymorphism

[Source](https://refactoring.guru/replace-conditional-with-polymorphism)

### Problem

Branches choose behavior from an object's type, field, or method result,
especially across repeated
[Switch Statements](../smells/object-orientation.md#switch-statements).

### Solution

- Reuse suitable existing classes. Fixed type →
  [subclasses](organizing-data.md#replace-type-code-with-subclasses); changing
  or independent variants →
  [State/Strategy](organizing-data.md#replace-type-code-with-statestrategy).
- Conditional mixed with other work → extract it into one method. Move each
  branch into the matching class's implementation; call the shared method.
- Once every case has moved, remove the conditional; make the shared method
  abstract if it has no remaining default behavior.
- Preserve default/error cases; retain a simple conditional when abstraction
  adds no value.

## Remove Control Flag

[Source](https://refactoring.guru/remove-control-flag)

### Problem

A boolean flag exists solely to steer local execution.

### Solution

- Stop a loop → `break`; skip the remaining iteration → `continue`; finish the
  operation → `return`.
- Replace the flag assignment at the correct exit point; remove obsolete flag
  declarations and checks.
- Preserve cleanup and effects that originally ran before or after the exit.

## Replace Nested Conditional with Guard Clauses

[Source](https://refactoring.guru/replace-nested-conditional-with-guard-clauses)

### Problem

Nested special cases obscure the normal execution path.

### Solution

- Case that ends the operation → move its return or throw before the main path,
  keeping check priority and cleanup.
- Effects prevent rearrangement →
  [Separate Query from Modifier](method-calls.md#separate-query-from-modifier)
  where behavior permits.
- Guards share one outcome →
  [Consolidate Conditional Expression](#consolidate-conditional-expression)
  after checking equivalence.

## Introduce Null Object

[Source](https://refactoring.guru/introduce-null-object)

### Problem

Repeated absence checks implement the same legitimate neutral behavior.

### Solution

- Shared fallback → return an object with default behavior instead of `null`;
  implement the same operations with their existing fallback behavior.
- Fallback does not fit an existing operation → extract a common operation and
  implement its neutral case.
- Remove redundant checks. When callers must still distinguish absence, expose a
  check such as `isNull()` on both real and default objects; preserve errors. A
  new type must earn its complexity.

## Introduce Assertion

[Source](https://refactoring.guru/introduce-assertion)

### Problem

Correct execution relies on an internal condition that is only assumed or
described in a comment.

### Solution

- Violating the assumption indicates a programming defect → assert it at the
  relevant boundary.
- Keep assertion expressions free of side effects; disabling assertions must not
  change valid execution.
- User input or recoverable system failure → retain explicit validation/error
  handling. Assert only conditions that correct execution needs.
