# Moving Features Between Objects

## Move Method

[Source](https://refactoring.guru/move-method)

### Problem

Behavior uses another class's data more than its own, or moving it would remove
an unnecessary dependency between callers and its current class.

### Solution

- Inspect dependencies → move related fields and methods together when this
  avoids calls back to the old class. Preserve inherited or overridden behavior;
  keep the method in place if the recipient cannot support those differences.
- Move the body → use an appropriate recipient reference and keep an old
  forwarding method initially.
- Migrate callers → update imports and public contracts; remove forwarding only
  when compatible.

## Move Field

[Source](https://refactoring.guru/move-field)

### Problem

A field is used mainly by another class and belongs beside those methods.

### Solution

- Public field → [encapsulate access](organizing-data.md#encapsulate-field)
  before moving storage.
- Establish the recipient → add the field and accessors, using a suitable
  existing reference when possible.
- Redirect all access → include subclasses, initialization, and persistence;
  remove the old field after migration.

## Extract Class

[Source](https://refactoring.guru/extract-class)

### Problem

A class mixes responsibilities that deserve separate ownership, often growing
into a [Large Class](../smells/bloaters.md#large-class).

### Solution

- Choose the boundary → create the new owner and prefer a one-way relationship.
- Move incrementally → transfer related fields and methods, starting with
  private methods; verify each move.
- Recheck the split → rename classes whose purpose changed and remove
  unnecessary links between them; avoid splitting a useful responsibility.
- Choose exposure → hide or expose the new owner according to invariants,
  identity, and client needs.

## Inline Class

[Source](https://refactoring.guru/inline-class)

### Problem

A class has lost its meaningful responsibility and independent lifecycle.

### Solution

- Prepare the recipient → expose the donor's needed operations through temporary
  forwarding.
- Migrate users → redirect references, then move fields and methods
  incrementally.
- Remove the empty donor → only after checking public contracts,
  identity-sensitive callers, construction, and persistence; retain genuinely
  independent lifetimes.

## Hide Delegate

[Source](https://refactoring.guru/hide-delegate)

### Problem

Clients traverse an owner's collaborators to reach required behavior.

### Solution

- Add narrow forwarding → expose the needed operation on the owner and migrate
  clients.
- Hide navigation → remove collaborator access only when clients no longer need
  it.
- Excessive forwarding → consider [Remove Middle Man](#remove-middle-man);
  retain a boundary only while it protects useful knowledge.

## Remove Middle Man

[Source](https://refactoring.guru/remove-middle-man)

### Problem

An owner mostly forwards calls without providing a useful boundary.

### Solution

- Expose the collaborator → provide an appropriate access path for clients.
- Redirect calls → let clients invoke the collaborator and remove redundant
  forwarding.
- No responsibility remains → consider [Inline Class](#inline-class) rather than
  keeping an empty owner.
- Check the tradeoff → preserve authorization, lifecycle controls, and public
  compatibility; [Hide Delegate](#hide-delegate) remains appropriate when
  coupling would be harmful.

## Introduce Foreign Method

[Source](https://refactoring.guru/introduce-foreign-method)

### Problem

An unmodifiable library type lacks one useful operation.

### Solution

- Add a local helper → pass the library object explicitly unless already
  accessible.
- Extract repeated behavior → use supported public operations and document why
  the helper lives outside its natural owner.
- Several reusable additions → prefer
  [Introduce Local Extension](#introduce-local-extension) instead of scattering
  helpers.

## Introduce Local Extension

[Source](https://refactoring.guru/introduce-local-extension)

### Problem

An unmodifiable type needs several related operations across clients.

### Solution

- Choose representation → wrap the object, or subclass when the library supports
  inheritance.
- Preserve construction → support normal creation and adaptation of existing
  objects; forward required public operations.
- Consolidate additions → move foreign methods and migrate relevant clients,
  checking identity, equality, and upstream compatibility.
