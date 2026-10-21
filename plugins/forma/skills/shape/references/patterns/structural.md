# Structural Patterns

## Adapter

[Source](https://refactoring.guru/design-patterns/adapter)

### Problem

Useful existing functionality exposes an interface incompatible with its
clients.

### Solution

- When the service cannot reasonably change, wrap it behind the client's
  interface; translate calls and data while preserving error contracts.
- Use composition by default; class adapters inherit both sides where the
  language permits it.
- When existing subclasses lack shared functionality that cannot go in their
  superclass, add it in one adapter wrapping their common contract.
- If both sides are safely changeable, align them directly; use
  [Decorator](#decorator) for extra behavior through the same interface.

## Bridge

[Source](https://refactoring.guru/design-patterns/bridge)

### Problem

High-level behavior and implementation details vary independently, making one
class hard to change or multiplying subclasses for their combinations.

### Solution

- Separate high-level policy from interchangeable implementations; connect them
  through composition and a stable implementation contract.
- Let clients choose compatible combinations; either dimension can then change
  independently, and implementations may switch at runtime.
- Keep the current structure when the two parts do not need to vary separately;
  use [Adapter](#adapter) to connect existing incompatible interfaces.

## Composite

[Source](https://refactoring.guru/design-patterns/composite)

### Problem

Clients need uniform operations over both individual objects and nested groups.

### Solution

- When the domain is a tree, give leaves and containers the same meaningful
  operation contract.
- Containers delegate recursively to children and combine results; preserve
  traversal order and prevent cycles.
- Keep child-management operations on containers unless uniform editing is
  necessary; avoid forcing unrelated objects into an overly general interface.

## Decorator

[Source](https://refactoring.guru/design-patterns/decorator)

### Problem

Individual objects need extra behavior, runtime combinations, or an alternative
to unavailable or unwieldy inheritance.

### Solution

- Wrap components in objects implementing the same interface; delegate while
  adding behavior before or after the wrapped call.
- Let clients choose layers, including wrapping classes that cannot be extended.
- Keep simple shared behavior direct; layered wrappers complicate removal and
  configuration, so verify ordering, identity expectations, errors and cleanup.

## Facade

[Source](https://refactoring.guru/design-patterns/facade)

### Problem

Common tasks expose clients to too many details of a complex subsystem.

### Solution

- Expose common tasks through a narrow entrypoint; coordinate subsystem calls
  and manage lifecycle only when callers do not.
- Use separate facades for coherent layers or unrelated needs; avoid one object
  collecting every responsibility.
- Keep necessary advanced access available. Choose [Adapter](#adapter) for
  interface compatibility; subsystem components need not know about a facade.

## Flyweight

[Source](https://refactoring.guru/design-patterns/flyweight)

### Problem

Many similar objects consume excessive memory by duplicating the same state.

### Solution

- Measure first, then share fields whose values stay fixed across similar
  objects; keep each instance's other fields in a separate context.
- Pass that context into operations. If a lookup pool is useful, key it by the
  shared values and return an existing flyweight when they match.
- Bound pool lifetime and measure the result: reduced memory can cost lookup or
  recomputation time and more complex ownership.

## Proxy

[Source](https://refactoring.guru/design-patterns/proxy)

### Problem

A service needs controlled access through its existing interface.

### Solution

- Implement the service contract and delegate through a proxy for lazy creation,
  authorization, remote access, logging or caching.
- If it owns the service, manage initialization and release there; define cache
  validity and preserve failure behavior.
- Account for added latency; use [Decorator](#decorator) for client-selected
  behavior layers rather than service access or lifecycle control.
