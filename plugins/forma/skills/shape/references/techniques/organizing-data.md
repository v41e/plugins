# Organizing Data

## Change Value to Reference

[Source](https://refactoring.guru/change-value-to-reference)

### Problem

Copies of one entity need shared identity and synchronized updates.

### Solution

- Control creation → use a factory that looks up and returns the shared object
  instead of creating another copy.
- Choose lifetime → preload entities or create them on demand; define
  missing-entity behavior.
- Return shared references → preserve identity and equality expectations,
  handling concurrent creation and updates consistently.

## Change Reference to Value

[Source](https://refactoring.guru/change-reference-to-value)

### Problem

Tracking a shared instance adds work for a small object whose data rarely
changes.

### Solution

- Remove mutation → initialize fields during construction and replace values
  instead of changing them.
- Define value comparison → implement compatible equality and hashing.
- Simplify creation → allow independent construction when safe; retain
  references when consumers require shared updates rather than independent
  copies.

## Duplicate Observed Data

[Source](https://refactoring.guru/duplicate-observed-data)

### Problem

Presentation objects own domain data and business logic.

### Solution

- Prepare UI access → route field reads and writes through accessors, then move
  domain data and business logic into a separate class.
- Keep a display copy → send UI edits to the domain object; refresh displayed
  values when it changes without sending those refreshes back as new edits.
- Persistent views → use [Observer](../patterns/behavioral.md#observer) or
  existing bindings; update displays without recursive writes and clean up
  subscriptions.
- Request-scoped views → synchronize explicitly instead of retaining observers
  across lifetimes; preserve validation and ordering.

## Self Encapsulate Field

[Source](https://refactoring.guru/self-encapsulate-field)

### Problem

Direct private-field access obstructs lazy computation, validation, or supported
overrides.

### Solution

- Add controlled access → create a getter and an optional setter.
- Redirect internal uses → preserve initialization order and avoid calling
  overrides on partially constructed objects.
- Fixed values → omit setters; retain direct access when accessor flexibility
  brings no useful benefit.

## Replace Data Value with Object

[Source](https://refactoring.guru/replace-data-value-with-object)

### Problem

A primitive field has acquired related data and behavior.

### Solution

- Hide direct field access → keep the original reader returning the simple
  value, and make its writer construct the new object.
- Create a value type → move the field and its behavior behind a constructor and
  reader, with no setter; initialize stored values in the original constructor
  as well as later assignments.
- Migrate storage → change the field's type; preserve validation and external
  representation.
- Entity identity → consider
  [Change Value to Reference](#change-value-to-reference); ordinary values need
  no shared identity.

## Replace Array with Object

[Source](https://refactoring.guru/replace-array-with-object)

### Problem

Array positions stand for different fields instead of items of the same kind.

### Solution

- Introduce a record → initially retain the array behind meaningful accessors.
- Migrate each position → replace indexed reads and writes, then move storage
  into named fields.
- Remove obsolete storage → preserve parsing and external ordering; keep arrays
  for sequences of the same kind of item.

## Change Unidirectional Association to Bidirectional

[Source](https://refactoring.guru/change-unidirectional-association-to-bidirectional)

### Problem

Both owners need navigation, but only one stores the relationship.

### Solution

- Check necessity → calculate reverse lookup when cheap; stored reverse links
  increase coupling.
- Choose one update owner → add the reverse field and a narrow helper on the
  other side.
- Route all mutations through that owner → keep reassignment, deletion, and
  failed updates consistent without recursive calls.

## Change Bidirectional Association to Unidirectional

[Source](https://refactoring.guru/change-bidirectional-association-to-unidirectional)

### Problem

One direction of a relationship adds little useful navigation.

### Solution

- Verify alternatives → remove unused navigation, pass the associated object, or
  obtain it through a lookup.
- Migrate remaining uses → preserve behavior and acceptable lookup costs.
- Remove maintenance code and field → update both sides together, preserving
  deletion rules, referential integrity, and serialization.

## Encapsulate Field

[Source](https://refactoring.guru/encapsulate-field)

### Problem

Public field access exposes representation and bypasses owner invariants.

### Solution

- Introduce access operations → redirect readers and writers before making the
  field private.
- Keep behavior nearby → move relevant validation or operations into the owner;
  migrate serializers and public consumers.
- Measured hot path → retain direct access when accessor overhead materially
  outweighs the boundary's benefit.

## Encapsulate Collection

[Source](https://refactoring.guru/encapsulate-collection)

### Problem

Collection getters and setters allow uncontrolled mutation or wholesale
replacement.

### Solution

- Control mutation → initialize storage and expose appropriate add, remove, and
  explicit replacement operations.
- Migrate clients → redirect mutations previously performed through getters or
  setters.
- Protect reads → choose a read-only view or copy; preserve ordering, aliasing
  expectations, and element mutability.
- Repeated client operations on the collection → move them into the owner when
  that gives it control over its own data.

## Replace Magic Number with Symbolic Constant

[Source](https://refactoring.guru/replace-magic-number-with-symbolic-constant)

### Problem

A literal has domain meaning that its spelling does not reveal.

### Solution

- Name the meaning → introduce a constant with appropriate units and scope.
- Replace selectively → inspect each occurrence; identical numbers may represent
  unrelated rules.
- Choose alternatives → retain obvious literals, derive available quantities,
  and use [type-code refactorings](#replace-type-code-with-class) for
  categorical values.

## Replace Type Code with Class

[Source](https://refactoring.guru/replace-type-code-with-class)

### Problem

Primitive category codes need type safety without distinct behavioral dispatch.

### Solution

- Model valid categories → use an enum or immutable type with controlled
  construction.
- Migrate fields and callers → replace raw constants, preserving serialized
  codes and unknown-value handling.
- Behavior varies by category → consider
  [subclasses](#replace-type-code-with-subclasses) or
  [State/Strategy](#replace-type-code-with-statestrategy) instead of merely
  wrapping the code.

## Replace Type Code with Subclasses

[Source](https://refactoring.guru/replace-type-code-with-subclasses)

### Problem

Stable type codes select distinct behavior across repeated conditionals.

### Solution

- Check fit → classification must remain fixed and fit the existing inheritance
  structure; otherwise use
  [State/Strategy](#replace-type-code-with-statestrategy).
- Centralize creation → select the subtype in a factory and move variant fields
  and methods.
- Replace the stored code → let each subtype's reader return its code; remove
  the redundant field from the parent.
- Replace dispatch branches → call the subtype's behavior instead; preserve
  parent contracts, variant coverage, construction, and serialized codes.

## Replace Type Code with State/Strategy

[Source](https://refactoring.guru/replace-type-code-with-state-strategy)

### Problem

Behavioral categories change during an object's life or cannot use inheritance.

### Solution

- Choose the role → [Strategy](../patterns/behavioral.md#strategy) selects
  algorithms; [State](../patterns/behavioral.md#state) manages lifecycle
  behavior and transitions.
- Introduce a delegate factory → select a delegate from the code and store it
  instead of the raw code; let its reader supply any code callers still need.
- Move variant behavior → call the delegate instead of branching on codes, and
  replace the delegate when the code changes.
- Keep it proportionate → simple cases may use callables or tables; preserve
  transition rules and unknown-code handling.

## Replace Subclass with Fields

[Source](https://refactoring.guru/replace-subclass-with-fields)

### Problem

Subclasses differ only through methods returning constant data.

### Solution

- Centralize creation → replace subclass construction with factories on the
  parent.
- Move variation into fields → initialize values in the parent constructor and
  retain compatible readers.
- Remove subclasses → first preserve extra constructor work, serialized
  discriminators, and callers relying on concrete types; retain genuine
  behavioral variants.
