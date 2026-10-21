# Couplers

## Feature Envy

[Source](https://refactoring.guru/smells/feature-envy)

### Problem

A method uses another object's data more than its own object's data.

### Solution

- **The whole operation belongs elsewhere:**
  [Move Method](../techniques/moving-features.md#move-method).
- **Only one fragment belongs elsewhere:**
  [Extract Method](../techniques/composing-methods.md#extract-method), then
  [Move Method](../techniques/moving-features.md#move-method).
- **Several objects supply the data:** Move the method to the class holding most
  of the data it uses, or extract parts for their respective data owners.
- **Behavior intentionally varies separately:** Preserve
  [Strategy](../patterns/behavioral.md#strategy),
  [Visitor](../patterns/behavioral.md#visitor), or legitimate orchestration
  boundaries.

## Inappropriate Intimacy

[Source](https://refactoring.guru/smells/inappropriate-intimacy)

### Problem

A class reaches into another class's internal fields or methods, so changes to
those details can break its caller.

### Solution

- **Members belong to the other class:**
  [Move Method](../techniques/moving-features.md#move-method) and
  [Move Field](../techniques/moving-features.md#move-field), only if the
  original owner can relinquish them.
- **Shared responsibility needs an explicit boundary:**
  [Extract Class](../techniques/moving-features.md#extract-class) for the shared
  parts, or [Hide Delegate](../techniques/moving-features.md#hide-delegate) to
  expose needed operations without revealing internal relationships.
- **Mutual navigation is unnecessary:**
  [Change Bidirectional Association to Unidirectional](../techniques/organizing-data.md#change-bidirectional-association-to-unidirectional).
- **Inheritance exposes internals without a valid subtype relationship:**
  [Replace Inheritance with Delegation](../techniques/generalization.md#replace-inheritance-with-delegation).

## Incomplete Library Class

[Source](https://refactoring.guru/smells/incomplete-library-class)

### Problem

An unmodifiable library class lacks operations its callers need.

### Solution

- **Only a few operations are missing:** Add client-side helpers with
  [Introduce Foreign Method](../techniques/moving-features.md#introduce-foreign-method).
- **Many related additions are needed:** Gather them in a wrapper or supported
  subclass with
  [Introduce Local Extension](../techniques/moving-features.md#introduce-local-extension).
- **Extension upkeep exceeds its benefit:** Keep a small local adaptation;
  reassess compatibility when the library changes.

## Message Chains

[Source](https://refactoring.guru/smells/message-chains)

### Problem

Callers navigate several collaborators and become dependent on their internal
arrangement.

### Solution

- **Navigation exposes replaceable relationships:**
  [Hide Delegate](../techniques/moving-features.md#hide-delegate).
- **The caller only needs an operation on the final object:**
  [Extract Method](../techniques/composing-methods.md#extract-method), then
  [Move Method](../techniques/moving-features.md#move-method) toward the start
  of the chain.
- **Hiding adds meaningless forwarding:** Keep clear traversal, including fluent
  APIs, rather than creating a [Middle Man](#middle-man).

## Middle Man

[Source](https://refactoring.guru/smells/middle-man)

### Problem

A class forwards operations without contributing a useful contract or
responsibility.

### Solution

- **Delegation adds no useful boundary:** Let clients call the delegate directly
  with [Remove Middle Man](../techniques/moving-features.md#remove-middle-man).
- **Delegation isolates dependencies or supplies real behavior:** Preserve
  useful [Proxy](../patterns/structural.md#proxy),
  [Decorator](../patterns/structural.md#decorator), policy, and compatibility
  boundaries.
