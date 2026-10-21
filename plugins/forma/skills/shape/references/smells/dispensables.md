# Dispensables

## Comments

[Source](https://refactoring.guru/smells/comments)

### Problem

Comments compensate for obscure expressions, operations, or unstated invariants.

### Solution

- **An expression needs explanation:**
  [Extract Variable](../techniques/composing-methods.md#extract-variable).
- **A coherent section needs explanation:**
  [Extract Method](../techniques/composing-methods.md#extract-method).
- **An existing method's name hides its purpose:**
  [Rename Method](../techniques/method-calls.md#rename-method).
- **A comment states an internal invariant:**
  [Introduce Assertion](../techniques/conditionals.md#introduce-assertion);
  retain production validation at trust boundaries.
- **Rationale, unavoidable algorithm complexity, or API contracts need
  explanation:** Preserve useful documentation.

## Duplicate Code

[Source](https://refactoring.guru/smells/duplicate-code)

### Problem

Code fragments look alike or perform the same job, so a change may need to be
repeated in several places.

### Solution

- **Methods in one class duplicate work:**
  [Extract Method](../techniques/composing-methods.md#extract-method).
- **Sibling subclasses duplicate work:**
  [Extract Method](../techniques/composing-methods.md#extract-method), then
  [Pull Up Method](../techniques/generalization.md#pull-up-method) and necessary
  [Pull Up Field](../techniques/generalization.md#pull-up-field).
- **Sibling constructors duplicate initialization:**
  [Pull Up Constructor Body](../techniques/generalization.md#pull-up-constructor-body).
- **Algorithm steps vary within a common sequence:**
  [Form Template Method](../techniques/generalization.md#form-template-method).
- **Different algorithms fulfill the same contract:**
  [Substitute Algorithm](../techniques/composing-methods.md#substitute-algorithm),
  choosing the clearer suitable implementation.
- **Separate classes share valid inherited behavior:**
  [Extract Superclass](../techniques/generalization.md#extract-superclass).
- **Inheritance is unsuitable:**
  [Extract Class](../techniques/moving-features.md#extract-class) for a shared
  component.
- **Different predicates lead to the same action:**
  [Consolidate Conditional Expression](../techniques/conditionals.md#consolidate-conditional-expression),
  then [Extract Method](../techniques/composing-methods.md#extract-method) if
  naming helps.
- **Every branch repeats the same work:**
  [Consolidate Duplicate Conditional Fragments](../techniques/conditionals.md#consolidate-duplicate-conditional-fragments).
- **Sharing obscures meaning or couples independent rules:** Keep the copies.

## Data Class

[Source](https://refactoring.guru/smells/data-class)

### Problem

A class only stores data and exposes fields, getters, or setters; callers
contain the operations and rules for that data.

### Solution

- **Public fields bypass invariants:**
  [Encapsulate Field](../techniques/organizing-data.md#encapsulate-field).
- **Exposed collections permit uncontrolled mutation:**
  [Encapsulate Collection](../techniques/organizing-data.md#encapsulate-collection).
- **Client behavior belongs with the data:**
  [Move Method](../techniques/moving-features.md#move-method), using
  [Extract Method](../techniques/composing-methods.md#extract-method) for
  relevant fragments.
- **New operations make broad access unnecessary:**
  [Remove Setting Method](../techniques/method-calls.md#remove-setting-method)
  or [Hide Method](../techniques/method-calls.md#hide-method), preserving
  supported callers.
- **Records, DTOs, or schemas deliberately carry data:** Keep their data-only
  role.

## Dead Code

[Source](https://refactoring.guru/smells/dead-code)

### Problem

Obsolete variables, branches, methods, types, or files obscure active behavior.

### Solution

- **Code appears unused:** Check analysis results against exports, reflection,
  configuration, and external consumers.
- **Code or files are proven unnecessary:** Delete them.
- **A class is unnecessary but some behavior remains:**
  [Inline Class](../techniques/moving-features.md#inline-class) or
  [Collapse Hierarchy](../techniques/generalization.md#collapse-hierarchy).
- **An argument is unnecessary:**
  [Remove Parameter](../techniques/method-calls.md#remove-parameter).

## Lazy Class

[Source](https://refactoring.guru/smells/lazy-class)

### Problem

A class adds maintenance and navigation without a meaningful responsibility.

### Solution

- **A standalone component adds little meaning:**
  [Inline Class](../techniques/moving-features.md#inline-class).
- **Adjacent hierarchy levels barely differ:**
  [Collapse Hierarchy](../techniques/generalization.md#collapse-hierarchy).
- **A small class protects a real boundary or concrete planned responsibility:**
  Keep it when that clarity outweighs indirection.

## Speculative Generality

[Source](https://refactoring.guru/smells/speculative-generality)

### Problem

Unused abstractions and options complicate current work for hypothetical
requirements.

### Solution

- **An abstract hierarchy level adds no needed variation:**
  [Collapse Hierarchy](../techniques/generalization.md#collapse-hierarchy).
- **A class only delegates unnecessarily:**
  [Inline Class](../techniques/moving-features.md#inline-class).
- **A method wrapper adds no meaning:**
  [Inline Method](../techniques/composing-methods.md#inline-method); delete
  truly unused methods directly.
- **Parameters or fields are unused:**
  [Remove Parameter](../techniques/method-calls.md#remove-parameter), or delete
  the fields.
- **Framework consumers or meaningful tests rely on the surface:** Preserve it
  until those requirements are understood.
