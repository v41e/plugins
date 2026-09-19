# Implement

Superpowers skills for the Locus Implement stage.

## Skills

| Use when                                                                                              | Skill                                     | Boundary                                                       |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------- | -------------------------------------------------------------- |
| Changed behavior supports an executable regression or acceptance check                                | `superpowers:test-driven-development`     | Use the relevant test tools and repository verification policy |
| Two or more ad hoc tasks are independent and no plan executor owns them                               | `superpowers:dispatching-parallel-agents` | Review results and conflicts; run affected and required checks |
| An approved plan has mostly independent tasks, stays here, and per-task review justifies the overhead | `superpowers:subagent-driven-development` | Use its task reviewer after every task                         |
| An approved plan runs in a separate task                                                              | `superpowers:executing-plans`             | Do not stack plan executors                                    |
| A check fails unexpectedly or observed behavior is unexplained                                        | `superpowers:systematic-debugging`        | Return to root-cause diagnosis                                 |

## Rules

- Choose one plan executor.
- Parallelize only independent work; keep coupled writes sequential.
