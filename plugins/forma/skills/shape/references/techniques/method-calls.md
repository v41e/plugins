# Simplifying Method Calls

## Add Parameter

[Source](https://refactoring.guru/add-parameter)

### Problem

An operation lacks information its callers must supply.

### Solution

- Per-call data → add a parameter; existing accessible data or stable owned
  state → reconsider whether another argument is needed.
- Update callers and hierarchy signatures together.
- Published API → retain a forwarding method when a valid default exists;
  otherwise keep the old contract until callers can migrate. Avoid growing a
  [Long Parameter List](../smells/bloaters.md#long-parameter-list).

## Remove Parameter

[Source](https://refactoring.guru/remove-parameter)

### Problem

An argument no longer contributes to the operation's contract.

### Solution

- Unused across every implementation → remove it from the signature and callers;
  retain any required effects from argument evaluation.
- A superclass/subclass implementation needs it → keep the shared contract.
- Published API → forward the old signature during migration; remove only after
  compatibility obligations end.

## Rename Method

[Source](https://refactoring.guru/rename-method)

### Problem

An operation's name does not explain its purpose or effects.

### Solution

- Choose a name describing the actual contract; update callers, imports,
  hierarchy declarations, and reflective uses.
- Incremental migration → introduce the new name and forward the old method to
  it.
- Published API → deprecate the old entrypoint instead of deleting it
  prematurely.

## Separate Query from Modifier

[Source](https://refactoring.guru/separate-query-from-modifier)

### Problem

A method returns a value and also changes externally visible state.

### Solution

- Independent observation needed → extract a query without observable mutation;
  retain updates in a command.
- Migrate callers to both operations in the original order, preserving whether
  the returned value describes pre-update or post-update state.
- Private caching with no observable change → keep it inside the query.
- Atomic operations or command results → keep combined behavior when splitting
  introduces races or loses meaningful results.

## Parameterize Method

[Source](https://refactoring.guru/parameterize-method)

### Problem

Methods duplicate an operation while varying only a value.

### Solution

- Same operation → replace the differing value with a parameter; migrate each
  caller with its original value.
- Only part is shared → extract that part rather than merge entire methods.
- Parameter selects unrelated actions →
  [Replace Parameter with Explicit Methods](#replace-parameter-with-explicit-methods)
  instead of growing a flag-driven conditional.

## Introduce Parameter Object

[Source](https://refactoring.guru/introduce-parameter-object)

### Problem

[Data Clumps](../smells/bloaters.md#data-clumps) repeat across parameter lists.

### Solution

- Coherent group → introduce an immutable value object with meaningful names;
  preserve validation and defaults.
- Add the object argument, then replace old parameters one at a time and update
  callers.
- Related calculations belong with the values →
  [Move Method](moving-features.md#move-method); keep a simple record when
  behavior adds nothing.

## Preserve Whole Object

[Source](https://refactoring.guru/preserve-whole-object)

### Problem

Callers unpack one object into several arguments.

### Solution

- Dependence on that object's interface is appropriate → pass it and retrieve
  required values inside the operation.
- Replace individual parameters incrementally; remove obsolete caller-side
  extraction.
- Multiple data sources or snapshot semantics matter → keep explicit values or
  [Introduce Parameter Object](#introduce-parameter-object). Preserve read
  timing and mutation permissions.

## Remove Setting Method

[Source](https://refactoring.guru/remove-setting-method)

### Problem

A field should remain fixed after construction, but exposes reassignment.

### Solution

- Setter immediately follows construction → pass that value to the constructor.
- Constructor calls the setter → initialize directly while retaining validation
  and required effects.
- Migrate deserialization and remaining consumers, then remove the setter and
  restrict field mutation. Required later changes mean this transformation does
  not fit.

## Replace Parameter with Explicit Methods

[Source](https://refactoring.guru/replace-parameter-with-explicit-methods)

### Problem

A selector hides distinct operations behind one method.

### Solution

- Caller already knows the intended action → extract a named method per branch;
  initially keep the old dispatcher forwarding to them.
- Migrate callers, then remove an unused dispatcher; preserve shared behavior,
  defaults, and errors.
- Dynamic selection or a clear, stable conditional remains useful → retain it.

## Replace Parameter with Method Call

[Source](https://refactoring.guru/replace-parameter-with-method-call)

### Problem

An argument merely forwards a query the receiver could perform.

### Solution

- All query inputs are available to the receiver → call it internally, then
  [Remove Parameter](#remove-parameter) and redundant caller-side calculations.
- Derivation is complex → first
  [Extract Method](composing-methods.md#extract-method).
- Caller-only inputs, snapshots, or different timing matter → keep the argument.
  Preserve evaluation count, effects, and dependency direction.

## Hide Method

[Source](https://refactoring.guru/hide-method)

### Problem

An internal operation exposes more API than its consumers need.

### Solution

- Used only internally → make private; subclasses require access → use the
  narrowest supported visibility.
- Search direct, reflective, framework, and extension uses before narrowing
  access; migrate supported external consumers first.
- A private accessor adds no behavior → consider removing it while preserving
  validation and hooks.

## Replace Constructor with Factory Method

[Source](https://refactoring.guru/replace-constructor-with-factory-method)

### Problem

Creation has complex setup or needs named modes, subtype selection, or
intentional instance reuse.

### Solution

- Wrap the existing constructor in a creation method; migrate creation sites,
  then restrict constructor access where compatible.
- Move selection, reuse, and other creation setup into the factory; keep field
  initialization in the constructor.
- Preserve initialization failures and identity expectations; adding caching
  changes behavior unless explicitly intended.

## Replace Error Code with Exception

[Source](https://refactoring.guru/replace-error-code-with-exception)

### Problem

An exceptional failure is awkwardly propagated as an ordinary result.

### Solution

- Exceptions fit the language and API → migrate one error case at a time: update
  handlers, replace the returned code, and document the exception.
- Preserve cleanup, recovery, and public compatibility during migration.
- Expected alternatives or established result/error conventions → retain them;
  exceptions must not become ordinary branching.

## Replace Exception with Test

[Source](https://refactoring.guru/replace-exception-with-test)

### Problem

Exception handling steers a predictable case with a reliable explicit check.

### Solution

- Stable condition → check before the operation and move the corresponding
  recovery into that branch.
- Verify equivalent edge cases, including both bounds where relevant; remove
  only the handling made redundant.
- State can change between check and use → retain atomic operation/error
  handling. Passing tests alone cannot prove exceptions impossible.
