# Behavioral Patterns

## Chain of Responsibility

[Source](https://refactoring.guru/design-patterns/chain-of-responsibility)

### Problem

Requests need different receivers or an ordered series of checks.

### Solution

- For receiver selection or reusable ordered checks, link handlers through one
  interface; each processes, forwards, or stops the request.
- For first-match dispatch, stop after acceptance; for pipelines, forward after
  successful checks. Define unhandled requests and failure behavior.
- Let clients compose or reorder handlers as needed. Keep direct calls when a
  simple receiver or sequence needs no reusable handling structure.

## Command

[Source](https://refactoring.guru/design-patterns/command)

### Problem

Senders need configurable operations without knowing their receivers, or
requests need deferred execution, reusable invocation, or undo.

### Solution

- Capture a request's receiver, operation, and required data behind a common
  execution interface; let senders hold and invoke interchangeable commands.
- Queue, schedule, log, or transmit commands when needed; define how execution
  data and receiver references survive serialization.
- For undo, keep history with a [Memento](#memento) or implement an inverse;
  irreversible effects need compensation.
- For simple callbacks, use a callable. Use [Strategy](#strategy) for
  interchangeable algorithms; define idempotency before retrying commands.

## Iterator

[Source](https://refactoring.guru/design-patterns/iterator)

### Problem

Consumers depend on collection internals or repeat traversal logic.

### Solution

- When traversal leaks or repeats, expose the native iteration protocol and keep
  progress in each iterator.
- For different traversals or independent passes, use separate iterators; define
  order, exhaustion, mutation behavior, and resource cleanup.
- For simple collections, keep native loops; custom abstractions can add cost.
  Use [Visitor](#visitor) for operations that vary by element type.

## Mediator

[Source](https://refactoring.guru/design-patterns/mediator)

### Problem

Dependencies between participants make their interactions difficult to change.

### Solution

- When peer dependencies obstruct change or reuse, route coordination through a
  mediator; participants notify it instead of knowing one another.
- Reuse an existing coordinator, such as a dialog; limit its interaction scope
  so it does not absorb unrelated responsibilities.
- For independent subscriptions, use [Observer](#observer); for a simpler
  subsystem entrance that leaves peer communication intact, use
  [Facade](structural.md#facade).

## Memento

[Source](https://refactoring.guru/design-patterns/memento)

### Problem

An object needs to save and restore its state without exposing private fields to
callers.

### Solution

- When undo or rollback needs snapshots, let the object create and restore them.
  Keep snapshot contents private and fixed; let another object manage history.
- For simple state with absent or safely reconnectable external references,
  consider copying or [Prototype](creational.md#prototype).
- Bound snapshot retention by recovery requirements and memory budget; restoring
  local state does not reverse external effects.

## Observer

[Source](https://refactoring.guru/design-patterns/observer)

### Problem

Consumers unknown to a publisher, or interested only temporarily, need
notifications when its state or behavior changes.

### Solution

- Maintain subscriptions through a shared callback contract; notify registered
  listeners and support unsubscription. Pass relevant event context or let
  listeners query the publisher.
- Reuse native event facilities or functions; if reactions require central
  coordination, use [Mediator](#mediator).
- Define delivery, failure, reentrancy, and cleanup behavior; rely on
  notification ordering only when the implementation guarantees it.

## State

[Source](https://refactoring.guru/design-patterns/state)

### Problem

Behavior and legal transitions depend on the current lifecycle state.

### Solution

- When repeated state conditionals scatter behavior, delegate to one active
  state object through a common interface.
- Transition by replacing the active state object; let the context or states
  initiate this. Preserve allowed transitions and effects; states may know
  successors, unlike independent strategies.
- For a small stable lifecycle, keep explicit branches or a transition table;
  use [Strategy](#strategy) for client-selected algorithms.

## Strategy

[Source](https://refactoring.guru/design-patterns/strategy)

### Problem

One task has interchangeable algorithms that change independently.

### Solution

- When algorithms vary, pass a strategy to a context that delegates through a
  shared input, output, and error contract.
- Let clients choose with knowledge of algorithm differences; strategies remain
  independent and do not own lifecycle transitions.
- Prefer callables where supported, or retain a small stable conditional. Use
  [Template Method](#template-method) for subclass variations of a fixed
  sequence.

## Template Method

[Source](https://refactoring.guru/design-patterns/template-method)

### Problem

Related algorithms share a sequence but differ in particular steps.

### Solution

- When subclasses share an algorithm's order, keep the template fixed and
  override individual steps. Require abstract steps, supply defaults for others,
  and use empty hooks for optional extensions.
- Reuse or introduce a base class for the shared sequence. Allow no-op overrides
  only when the step's contract permits them.
- If steps or their order vary independently, use composition; choose
  [Strategy](#strategy) for runtime replacement instead of multiplying hooks.

## Visitor

[Source](https://refactoring.guru/design-patterns/visitor)

### Problem

An operation spans different element types or auxiliary behavior obscures their
main responsibilities.

### Solution

- Group each operation in a visitor covering every element type; allow justified
  no-ops.
- Use double dispatch: each concrete element accepts the visitor and calls its
  matching visit method. Keep traversal explicit, optionally with
  [Iterator](#iterator).
- Add or reuse acceptance methods on elements; further operations can then use
  new visitors. Frequent element-type changes require updating every visitor.
- Keep ordinary methods when adequate, and preserve encapsulation when granting
  visitors data access.
