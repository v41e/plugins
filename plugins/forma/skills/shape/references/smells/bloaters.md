# Bloaters

## Long Method

[Source](https://refactoring.guru/smells/long-method)

### Problem

Too many steps in one method hide its purpose or make its logic hard to follow.

### Solution

- **A step needs an explanation or a loop hides the main task:** Use
  [Extract Method](../techniques/composing-methods.md#extract-method) when its
  name clarifies the operation.
- **Local variables prevent extraction:** Use
  [Replace Temp with Query](../techniques/composing-methods.md#replace-temp-with-query)
  when calculating again gives the same result and effects.
- **Related arguments prevent extraction:** Use
  [Introduce Parameter Object](../techniques/method-calls.md#introduce-parameter-object).
- **Arguments come from one object:** Use
  [Preserve Whole Object](../techniques/method-calls.md#preserve-whole-object)
  if the method can depend on that object.
- **Branch conditions and bodies hide the main task:** Use
  [Decompose Conditional](../techniques/conditionals.md#decompose-conditional).
- **Local variables still prevent splitting the method:** Use
  [Replace Method with Method Object](../techniques/composing-methods.md#replace-method-with-method-object).
- **One clear algorithm:** Keep it together; length alone does not justify
  extraction.

## Large Class

[Source](https://refactoring.guru/smells/large-class)

### Problem

Many fields and methods serve different tasks in one class, so changes affect
unrelated code.

### Solution

- **A group of fields and methods has its own task:** Use
  [Extract Class](../techniques/moving-features.md#extract-class).
- **Only some instances need a behavior, or implement it differently:** Use
  [Extract Subclass](../techniques/generalization.md#extract-subclass).
- **Callers need a defined set of operations:** Use
  [Extract Interface](../techniques/generalization.md#extract-interface).
- **UI code also stores business data and rules:** Move those rules out; use
  [Duplicate Observed Data](../techniques/organizing-data.md#duplicate-observed-data)
  only when synchronized copies are needed.
- **Fields and methods serve one task:** Keep the class together when splitting
  it would scatter rules that must hold across its fields.

## Primitive Obsession

[Source](https://refactoring.guru/smells/primitive-obsession)

### Problem

Numbers, strings, or array keys stand in for meaningful types or named fields.
Callers repeat the rules for interpreting and validating them.

### Solution

- **Values share business rules:** Use
  [Replace Data Value with Object](../techniques/organizing-data.md#replace-data-value-with-object).
- **Related values travel as arguments:** Use
  [Introduce Parameter Object](../techniques/method-calls.md#introduce-parameter-object)
  or
  [Preserve Whole Object](../techniques/method-calls.md#preserve-whole-object).
- **Codes stand for a fixed set of categories:** Use
  [Replace Type Code with Class](../techniques/organizing-data.md#replace-type-code-with-class).
- **A code stays fixed for an object's lifetime and selects behavior:** Use
  [Replace Type Code with Subclasses](../techniques/organizing-data.md#replace-type-code-with-subclasses),
  if callers can use each subclass through the same contract.
- **The category changes, or subclasses do not fit:** Use
  [Replace Type Code with State/Strategy](../techniques/organizing-data.md#replace-type-code-with-statestrategy).
- **Array positions or keys stand for different fields:** Use
  [Replace Array with Object](../techniques/organizing-data.md#replace-array-with-object).
- **Simple values or arrays of the same kind of item:** Keep their existing
  representation.

## Long Parameter List

[Source](https://refactoring.guru/smells/long-parameter-list)

### Problem

Many arguments hide how values relate or make calls easy to get wrong.

### Solution

- **The method can obtain a value from an object it already knows:** Use
  [Replace Parameter with Method Call](../techniques/method-calls.md#replace-parameter-with-method-call).
- **Arguments are fields of one object:** Use
  [Preserve Whole Object](../techniques/method-calls.md#preserve-whole-object).
- **Related arguments have different sources:** Use
  [Introduce Parameter Object](../techniques/method-calls.md#introduce-parameter-object).
- **Grouping would create unwanted dependencies:** Keep explicit inputs;
  argument count alone is insufficient.

## Data Clumps

[Source](https://refactoring.guru/smells/data-clumps)

### Problem

The same related values recur as fields or arguments in several places.

### Solution

- **Check that the values belong together:** If one value were missing, would
  the rest still describe the same thing? Group values that form one concept.
- **Repeated class fields:** Use
  [Extract Class](../techniques/moving-features.md#extract-class).
- **Repeated argument groups:** Use
  [Introduce Parameter Object](../techniques/method-calls.md#introduce-parameter-object).
- **Arguments already belong to an object:** Use
  [Preserve Whole Object](../techniques/method-calls.md#preserve-whole-object).
- **Operations belong with the grouped data:** Use
  [Move Method](../techniques/moving-features.md#move-method).
- **Passing the object would add an unwanted dependency:** Pass the required
  values instead.
