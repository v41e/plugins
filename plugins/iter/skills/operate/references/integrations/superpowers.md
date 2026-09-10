# Superpowers Integration

## Artifacts

Paths are relative to the project root. Project instructions and links override
defaults.

| Artifact | Default path               |
| -------- | -------------------------- |
| Drafts   | `docs/superpowers/drafts/` |
| Specs    | `docs/superpowers/specs/`  |
| Plans    | `docs/superpowers/plans/`  |

Missing paths need no setup. Reading artifacts requires no installed skills.

## Skills

Use installed skills for every matching condition. The mode owns order and gates.

| Condition                                              | Skill                                         |
| ------------------------------------------------------ | --------------------------------------------- |
| Reproducible bug or unexpected behavior                | `$superpowers:systematic-debugging`           |
| Changed behavior supports an executable failing check  | `$superpowers:test-driven-development`        |
| Executing an approved written plan                     | `$superpowers:executing-plans`                |
| Applying review feedback                               | `$superpowers:receiving-code-review`          |
| Material pre-merge review without an equivalent review | `$superpowers:requesting-code-review`         |
| About to claim completion                              | `$superpowers:verification-before-completion` |

Do not add delegation, worktrees, plans, or review ceremony unless the task and
repository policy require them.
