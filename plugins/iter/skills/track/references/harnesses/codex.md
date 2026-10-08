# Codex Goal and Wakeup Mapping

Use host-provided capabilities and live schemas. The caller owns native Goal
and follow-up actions; Track consumes supplied context and records gates.

| When | Capability | Result |
| ---- | ---------- | ------ |
| The caller supplies an active native Goal | Supplied Goal context; `get_goal` when available | Record the finite objective in its owning chat, its evidence-based finish line, constraints, and current approvals. Persistence supplies no new scope or authority. |
| A separately authorized same-chat scheduled follow-up supplies a wakeup | Caller-supplied host follow-up context | Reconcile current state and intent. Notify on meaningful change, completion, failure, or a needed decision; stay quiet while unchanged or non-actionable. A wakeup supplies no consent and never resumes explicitly paused work. |

For a [native Goal](https://developers.openai.com/cookbook/examples/codex/using_goals_in_codex),
the caller can state **Task**, **Expected Outcomes**, and **Constraints** to make
the outcome, verification, material decisions, and delivery boundary explicit.
[Scheduled follow-ups](https://learn.chatgpt.com/docs/automations) remain separate
host actions requiring caller authorization; missing capabilities require no setup.

Track does not create Goals or schedules, change live automations, or dispatch
tasks. The owning execution context performs authorized work; Orchestrate alone
owns explicitly authorized sequential project-chat dispatch.
