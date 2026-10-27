# Superpowers Method Mapping

Maintain uses methods in the owning execution context; Track records their
results.

| When | Capability | Result |
| ---- | ---------- | ------ |
| A defect or unexpected behavior needs diagnosis | `superpowers:systematic-debugging` | Reproduction and root cause before repair |
| Changed behavior supports an executable failing check | `superpowers:test-driven-development` | Meaningful regression or acceptance evidence |
| An approved written plan needs execution | `superpowers:executing-plans` | Scoped implementation and required checks within existing authorization |
| Supplied code review requests changes | `superpowers:receiving-code-review` | Verified feedback and correction evidence |
| Substantive or policy-required code review lacks equivalent evidence | `superpowers:requesting-code-review` | Evidence for the code-quality dimensions actually reviewed; spec/plan review remains distinct |
| Completion evidence is missing or stale | `superpowers:verification-before-completion` | Current verification of the actual result before a completion claim |

Methods inherit the caller's contract, authority, and repository policy. Reuse
equivalent evidence for the dimensions and revision actually reviewed. Missing
plugins require no setup; use the owning context's available methods.
