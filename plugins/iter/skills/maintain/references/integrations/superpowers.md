# Superpowers Method Mapping

Maintain uses methods in the owning execution context; Track records their
results.

| When | Capability | Result |
| ---- | ---------- | ------ |
| A defect or unexpected behavior needs diagnosis | `superpowers:systematic-debugging` | Reproduction and root cause before repair |
| Changed behavior supports an executable failing check | `superpowers:test-driven-development` | Meaningful regression or acceptance evidence |
| An approved written plan needs execution | `superpowers:executing-plans` | Scoped implementation and required checks within existing authorization |
| Supplied code review requests changes | `superpowers:receiving-code-review` | Verified feedback and correction evidence |
| Substantive or policy-required code review lacks equivalent evidence | `superpowers:requesting-code-review` | Code-defect evidence toward review of intent, behavior, contracts, docs, and simplicity; spec/plan review remains distinct |
| Completion evidence is missing or stale | `superpowers:verification-before-completion` | Current verification of the actual result before a completion claim |

Reuse equivalent evidence. Missing plugins require no setup. Plans, worktrees,
delegation, and review procedures follow actual need and repository policy.
The owning context obtains suitable independent artifact review; narrower method
evidence cannot stand in for judgment it did not supply.
