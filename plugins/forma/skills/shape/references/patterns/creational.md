# Creational Patterns

## Factory Method

[Source](https://refactoring.guru/design-patterns/factory-method)

### Problem

Product-using code must stay independent of concrete product classes while
subclasses customize creation.

### Solution

- Add an overridable creation method returning the shared product interface;
  reuse or introduce creator subclasses when this extension point is useful.
- Keep product-using logic in the superclass; overrides may construct or reuse
  compatible instances. The base method may be abstract or supply a default.
- Without subclass customization, prefer direct construction or an injected
  factory callable; weigh the added creator classes against the extension need.

## Abstract Factory

[Source](https://refactoring.guru/design-patterns/abstract-factory)

### Problem

Callers must create several related products in mutually compatible variants.

### Solution

- For interchangeable families, expose one creation operation per product type
  and supply one factory for the chosen family.
- Clients depend on product contracts; each factory keeps its outputs
  compatible. Extract family creation when it obscures another class's main job.
- For simple wiring, use a bundle of constructor callables; family factories add
  interfaces, and new product kinds affect every factory.

## Builder

[Source](https://refactoring.guru/design-patterns/builder)

### Problem

Complex construction scatters assembly code, needs many optional parameters, or
produces different representations through the same steps.

### Solution

- Separate assembly into builder steps; call only the steps a configuration
  needs. Concrete builders can produce unrelated result types.
- Reuse recurring sequences in an optional director; otherwise let callers
  invoke the steps.
- Expose completed results only. If named arguments or a small constructor
  suffice, keep them instead of adding builders.

## Prototype

[Source](https://refactoring.guru/design-patterns/prototype)

### Problem

Callers need copies of configured objects without knowing their concrete
classes.

### Solution

- Put cloning behind the object's interface so it can copy private state and
  preserve the concrete type.
- For repeated configurations, clone prepared prototypes instead of repeating
  initialization or adding subclasses only for presets; use a registry if
  needed.
- Define copy depth, cycles, identity and resource ownership; prefer native
  copying when it honors those rules.

## Singleton

[Source](https://refactoring.guru/design-patterns/singleton)

### Problem

One instance must be shared through a global access point within a defined
runtime scope.

### Solution

- When uniqueness is required, hide unrestricted construction and return the
  cached instance from one accessor.
- Make lazy initialization thread-safe and define shutdown; this does not
  establish uniqueness across processes.
- When only sharing is needed, construct once and inject it; global access hides
  dependencies and makes tests harder.
