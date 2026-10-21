# Change Preventers

## Divergent Change

[Source](https://refactoring.guru/smells/divergent-change)

### Problem

One class repeatedly changes for unrelated reasons.

### Solution

- **Responsibilities vary independently:**
  [Extract Class](../techniques/moving-features.md#extract-class).
- **Separate classes repeat behavior that fits a shared parent:**
  [Extract Superclass](../techniques/generalization.md#extract-superclass).
- **Only some objects need a related set of special behavior:**
  [Extract Subclass](../techniques/generalization.md#extract-subclass); avoid
  inheritance based solely on similar code.

## Parallel Inheritance Hierarchies

[Source](https://refactoring.guru/smells/parallel-inheritance-hierarchies)

### Problem

Adding a child class repeatedly requires a matching child class under another
parent.

### Solution

- **The paired classes can share one owner:** Make objects in one hierarchy
  refer to their counterparts in the other. Use
  [Move Method](../techniques/moving-features.md#move-method) and
  [Move Field](../techniques/moving-features.md#move-field) to move the referred
  objects' behavior and state into the corresponding referring classes; remove
  the resulting redundant hierarchy.
- **Consolidation makes the architecture harder to understand:** Retain the
  parallel structure.

## Shotgun Surgery

[Source](https://refactoring.guru/smells/shotgun-surgery)

### Problem

One change to a responsibility requires many small edits across classes.

### Solution

- **A suitable owner exists:**
  [Move Method](../techniques/moving-features.md#move-method) and
  [Move Field](../techniques/moving-features.md#move-field) into it.
- **No suitable owner exists:** Create a class for that responsibility, then
  move its methods and fields there.
- **Old classes become empty shells:**
  [Inline Class](../techniques/moving-features.md#inline-class).
- **Changes only propagate to necessary consumers or tests:** Keep those
  legitimate updates.
