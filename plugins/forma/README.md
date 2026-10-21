# Forma

## Overview

Forma guides code design, maintainability assessment, and behavior-preserving
refactoring. Shape connects a short diagnostic checklist to references covering
23 smells, 66 techniques, and 22 patterns.

## Structure

- [`skills/`](skills/): instruction-driven skills:
  - [`shape/`](skills/shape/): design, assessment, and refactoring
    - [`references/`](skills/shape/references/): smells, techniques, and
      patterns
  - [`using/`](skills/using/): plugin orientation
- [`plugin.json`](plugin.json): portable package identity
- [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json): Codex discovery and
  interface
- [`AGENTS.md`](AGENTS.md): package operating contract

## Quickstart

Install `forma` from the `v41e` marketplace in a compatible client and reload
its plugins. Invoke `forma:shape`; use `forma:using` for orientation.

## Sources

Names and catalogue coverage follow
[Refactoring.Guru](https://refactoring.guru/),
[Fowler's Refactoring](https://martinfowler.com/books/refactoring.html), and
[Design Patterns](https://www.informit.com/store/design-patterns-elements-of-reusable-object-oriented-software-9780201633610).
Descriptions and mappings are original. The pattern inventory follows
Refactoring.Guru's 22 entries.
