# Object-Orientation Abusers

## Alternative Classes with Different Interfaces

[Source](https://refactoring.guru/smells/alternative-classes-with-different-interfaces)

### Problem

Classes do the same work through differently named methods or incompatible
calling conventions.

### Solution

- **Only names differ:**
  [Rename Method](../techniques/method-calls.md#rename-method).
- **Methods live in different places or take different inputs:** Use
  [Move Method](../techniques/moving-features.md#move-method),
  [Add Parameter](../techniques/method-calls.md#add-parameter), or
  [Parameterize Method](../techniques/method-calls.md#parameterize-method) to
  align equivalent behavior.
- **Only part of the behavior is shared:**
  [Extract Superclass](../techniques/generalization.md#extract-superclass) when
  the resulting subtype relationship is valid.
- **A class becomes redundant:** Update its callers before removing it.
- **Separate libraries or incompatible semantics prevent unification:** Preserve
  the distinction; an [Adapter](../patterns/structural.md#adapter) may serve
  callers.

## Refused Bequest

[Source](https://refactoring.guru/smells/refused-bequest)

### Problem

A child class inherits methods or fields it cannot meaningfully use, sometimes
overriding methods just to reject calls or throw errors.

### Solution

- **Reuse is the only connection; the child cannot safely act as the parent:**
  [Replace Inheritance with Delegation](../techniques/generalization.md#replace-inheritance-with-delegation).
- **Both classes still support a smaller set of common behavior:** Use
  [Extract Superclass](../techniques/generalization.md#extract-superclass) for
  that behavior, with both classes inheriting directly from the new parent.
  Leave methods and fields that only one class needs in that class.
- **Inherited conveniences merely go unused:** Keep the hierarchy if the child
  can still safely serve as the parent type.

## Switch Statements

[Source](https://refactoring.guru/smells/switch-statements)

### Problem

A complex `switch` or chain of `if` checks is hard to follow, or repeated copies
must all change when a new case is added.

### Solution

- **The branches belong with another class's data:** Use
  [Extract Method](../techniques/composing-methods.md#extract-method), then
  [Move Method](../techniques/moving-features.md#move-method).
- **Type codes select behavior:**
  [Replace Type Code with Subclasses](../techniques/organizing-data.md#replace-type-code-with-subclasses)
  for stable types, or
  [Replace Type Code with State/Strategy](../techniques/organizing-data.md#replace-type-code-with-statestrategy)
  for changing roles.
- **Classes already provide the required alternative implementations:** Use
  [Replace Conditional with Polymorphism](../techniques/conditionals.md#replace-conditional-with-polymorphism).
- **A few cases call the same method with different arguments:** Use
  [Replace Parameter with Explicit Methods](../techniques/method-calls.md#replace-parameter-with-explicit-methods).
- **An absence case has defined default behavior:** Use
  [Introduce Null Object](../techniques/conditionals.md#introduce-null-object);
  preserve required failures.
- **Simple actions or choosing which class to create:** Keep clear branches,
  including [Factory Method](../patterns/creational.md#factory-method) and
  [Abstract Factory](../patterns/creational.md#abstract-factory) construction.

## Temporary Field

[Source](https://refactoring.guru/smells/temporary-field)

### Problem

Fields are populated only for certain operations or cases and remain empty the
rest of the time, making the object's expected state unclear.

### Solution

- **Fields and their methods form a separate task or case:** Move them together
  with [Extract Class](../techniques/moving-features.md#extract-class).
- **Fields hold one operation's inputs or working values:** Keep them local when
  possible; if those values prevent splitting the method, use
  [Replace Method with Method Object](../techniques/composing-methods.md#replace-method-with-method-object).
- **Repeated checks for missing values choose defined default behavior:** Use
  [Introduce Null Object](../techniques/conditionals.md#introduce-null-object),
  without hiding invalid or missing required state.
- **Optional fields describe real stages in the object's life:** Keep those
  stages explicit.
