# Dealing with Generalization

## Pull up Field

[Source](https://refactoring.guru/pull-up-field)

### Problem

Subclasses repeat fields used for the same purpose.

### Solution

- Equivalent fields → align names/types, declare once in the superclass, then
  remove subclass copies.
- Shared access needed → use the narrowest visibility or
  [Self Encapsulate Field](organizing-data.md#self-encapsulate-field).
- Verify initialization and serialization; matching names alone do not establish
  shared semantics.

## Pull up Method

[Source](https://refactoring.guru/pull-up-method)

### Problem

Subclasses repeat methods that can safely work for every affected child class.

### Solution

- Equivalent behavior → align bodies/signatures, move implementation upward, and
  remove redundant overrides.
- Subclass-only dependencies → pull up shared fields/methods, or declare
  abstract operations/accessors for genuine variation.
- Check assumptions and overridden calls for every affected child class; use the
  parent type in callers only when it provides everything they need.

## Pull up Constructor Body

[Source](https://refactoring.guru/pull-up-constructor-body)

### Problem

Subclass constructors repeat equivalent initialization of shared state.

### Solution

- Common initialization can safely run first → move it into a superclass
  constructor with only the parameters it needs.
- Keep subclass constructors calling the parent at the language-required point,
  then perform specialized initialization.
- Preserve ordering and failures; do not move work that requires initialized
  subclass state.

## Push Down Field

[Source](https://refactoring.guru/push-down-field)

### Problem

A superclass field is used only by some child classes.

### Solution

- One subclass owns it → declare there and remove the superclass field.
- Several subclasses need fields that will evolve differently → move a copy to
  each; fields used the same way may warrant a shared intermediate class
  instead.
- Migrate initialization and references; preserve persistence and inherited
  behavior before deleting the original field.

## Push Down Method

[Source](https://refactoring.guru/push-down-method)

### Problem

A superclass method is needed only by some child classes.

### Solution

- One subclass needs it → move the implementation there.
- Several, but not all, need identical behavior → consider an intermediate
  superclass instead of duplicating it.
- Update callers to use the appropriate child type or interface; preserve
  overridden calls. Remove the parent method only when its public contract
  permits.

## Extract Subclass

[Source](https://refactoring.guru/extract-subclass)

### Problem

Only some objects need a related group of the class's fields and methods.

### Solution

- Fixed special case that still satisfies the parent contract → create a child
  class, initialize through the parent, and update the relevant creation calls.
- [Push Down Method](#push-down-method), then
  [Push Down Field](#push-down-field) for specialized members.
- Override variant operations and remove obsolete selection flags once all their
  uses have moved to polymorphic dispatch.
- Choices vary independently or change during an object's life → use components,
  potentially [Strategy](../patterns/behavioral.md#strategy), instead of more
  subclasses.

## Extract Superclass

[Source](https://refactoring.guru/extract-superclass)

### Problem

Classes repeat fields and methods and can satisfy the same parent contract.

### Solution

- Valid common parent → create it, abstract when it should not be created
  directly; pull up shared fields, methods, and constructor work, starting with
  the fields those methods need.
- Migrate callers that need only the common contract.
- Existing inheritance prevents another parent → use composition;
  [Extract Interface](#extract-interface) when only a shared capability is
  needed. Preserve initialization and dispatch.

## Extract Interface

[Source](https://refactoring.guru/extract-interface)

### Problem

Several callers use the same subset of a class's methods, or different classes
provide the same operations.

### Solution

- Declare that capability as an interface/protocol; implement it in relevant
  classes and update consumer types.
- Keep implementation-specific operations out of the contract.
- Duplicate implementation remains →
  [Extract Class](moving-features.md#extract-class) for shared composition, or
  [Extract Superclass](#extract-superclass) when subtyping fits. An interface
  alone shares no code.

## Collapse Hierarchy

[Source](https://refactoring.guru/collapse-hierarchy)

### Problem

Adjacent hierarchy levels no longer express useful differences.

### Solution

- Remove subclass → pull members up; remove superclass → push members down.
- Redirect construction, type references, and remaining subclasses to the
  survivor; delete the empty class.
- Check that remaining child classes still satisfy their new parent's contract.
  Preserve public compatibility, dispatch, initialization, and serialized type
  identities.

## Form Template Method

[Source](https://refactoring.guru/form-template-method)

### Problem

Subclass algorithms share a stable sequence but vary in selected steps.

### Solution

- [Extract Method](composing-methods.md#extract-method) for each step; align
  names and signatures for equivalent roles.
- Pull up identical implementations; declare varying steps as abstract
  operations with subclass implementations.
- Pull up the method that calls those steps into a
  [Template Method](../patterns/behavioral.md#template-method), preserving step
  order and each step's expected inputs and effects.

## Replace Inheritance with Delegation

[Source](https://refactoring.guru/replace-inheritance-with-delegation)

### Problem

A child class needs only part of its parent's API, cannot inherit its data, or
cannot safely serve as the parent type; see
[Refused Bequest](../smells/object-orientation.md#refused-bequest).

### Solution

- Store an object of the former parent class in a field and call its methods for
  reused behavior; add forwarding methods for supported caller operations.
- Update callers that expect the parent type, then remove inheritance and
  initialize the field with the helper object.
- Preserve initialization, state sharing, and override/callback behavior;
  replacing `this` with another instance can change dispatch and identity.

## Replace Delegation with Inheritance

[Source](https://refactoring.guru/replace-delegation-with-inheritance)

### Problem

A wrapper forwards an entire API despite being a valid subtype.

### Solution

- Full contract and lifecycle fit, with no conflicting parent → inherit from the
  delegate type; align names and remove trivial forwarding methods.
- Replace delegate references with self, preserving initialization/state, then
  remove the delegate field.
- Partial API, replaceable/shared delegate, or incompatible newly exposed
  behavior → keep composition.
