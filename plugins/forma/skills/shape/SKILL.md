---
name: shape
description: Use when designing code structure, assessing maintainability, or refactoring a file or module, including code smells, responsibilities, interfaces, and design-pattern choices.
---

# Shape Code

## Purpose

Choose clear code structure with the smallest useful change.

## Input

Requested behavior or code scope; local conventions.

## Workflow

| Mode | Task |
| ---- | ---- |
| Design | Choose responsibilities, interfaces, and dependencies. |
| Refactor | Improve structure while preserving observable behavior. |

Infer the mode. Inspect relevant code, callers, and tests. Use the checklist
below; read only relevant reference entries. Match the condition before choosing
a treatment. Assessments stay read-only; implement when requested. Reuse the
caller's workflow.

## Output

Decision or change, concrete benefit, verification, and remaining limits.

## Rules

| Problem | Direction |
| ------- | --------- |
| Operation hard to follow? | Check [bloaters](references/smells/bloaters.md); [extract, inline, or name steps](references/techniques/composing-methods.md). |
| One change scattered across owners? | Check [change preventers](references/smells/change-preventers.md); [move responsibilities](references/techniques/moving-features.md). |
| Data relationships unclear? | [Group, encapsulate, or simplify data](references/techniques/organizing-data.md). |
| Inheritance violates expectations? | Check [object-orientation smells](references/smells/object-orientation.md); [reshape inheritance or delegate](references/techniques/generalization.md). |
| Branching hides intent? | [Simplify conditionals](references/techniques/conditionals.md). |
| Calls obscure inputs or effects? | [Clarify method contracts](references/techniques/method-calls.md). |
| Internal details leak? | Check [couplers](references/smells/couplers.md). |
| Code or indirection adds no value? | Check [dispensables](references/smells/dispensables.md). |
| Current variation needs structure? | Compare [creation](references/patterns/creational.md), [composition](references/patterns/structural.md), or [behavior](references/patterns/behavioral.md) options. |

- A smell invites inspection. Keep adequate code; justify each abstraction.
- Reuse existing code and language features; follow project conventions.
- Preserve validation, error handling, useful documentation, and safety.
- Refactoring preserves supported external contracts, serialization, observable
  identity, evaluation order, side effects, and failures. Internal interfaces
  may change when their callers migrate together. Separate behavior fixes. For
  infrastructure, preserve resource IDs/scopes, permissions, and lifecycle;
  compare synthesized artifacts.
- Verify affected contracts with focused checks.
