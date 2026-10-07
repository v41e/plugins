# Iter Workflows

Iter connects observations, work records, maintenance, and authorized dispatch.
Each skill has one owner; engineering methods remain in the project context.

| Skill | Owns | Result |
| ----- | ---- | ------ |
| [Brief](../skills/brief/SKILL.md) | Read-only judgment from goals, decisions, and selected evidence | Status, focus plan, or retrospective |
| [Track](../skills/track/SKILL.md) | Work contracts, approvals, evidence gates, and synchronization | Current state and missing evidence or handoff |
| [Maintain](../skills/maintain/SKILL.md) | Candidate selection, reconciliation, continuation, and stopping in an authorized owner | Verified repairs, documentation corrections, or a supported no-op |
| [Orchestrate](../skills/orchestrate/SKILL.md) | Authorized sequential dispatch to exact project-owned tasks | Owning task references and aggregate outcomes |

Track can be used directly for manual work. It records the results of engineering
methods such as Superpowers; it does not implement, debug, review code, or deliver
changes. Required records and artifact depth follow the current contract and
repository policy. Missing optional records require no setup.

Maintain checks signals against current state and existing ownership before
choosing work. An already owned outcome is resumed only when it belongs to this
assignment; another owner's work stays with that owner. Locus Find and Write can
help resolve content ownership and reconcile documentation when installed.

## Supervised work

The owning copilot investigates and recommends within the agreed outcome.
Compare native/library capabilities, workload, and established local patterns
before adding machinery. Choose routine defaults and disclose consequential
assumptions; present unsettled material product, architecture, contract,
ownership, security, and scope choices for a focused human decision. A reversible
choice can still be material. Questions and exploration do not grant execution;
continue independent authorized preparation while dependent choices wait.

[Track](../skills/track/SKILL.md) records substantive checkpoints inside existing
stages: independent final-artifact review and corrections precede a concise
summary, then separate human spec and plan/execution approvals. Task Scope and
Bug Triage apply the same checkpoints internally. Routine settled work stays
proportional. Summary approval covers its identified artifact; full reading adds
no gate. The execution context obtains reviews against original intent, accepted
decisions, and relevant local examples; checks alone do not prove alignment.

The [Plan](../skills/track/references/stages/plan.md) states delivery scope.
[Review](../skills/track/references/stages/review.md) records final review/checks
and covered PR publication before human PR review, unless an explicit local
checkpoint or publication hold applies. Reuse unchanged approvals/evidence;
reopen materially affected gates. Human integration decisions and verification
of the actual integrated result remain prerequisites for Complete.

## Interactive Goals

A [native Goal](https://developers.openai.com/cookbook/examples/codex/using_goals_in_codex)
is a finite objective in its owning chat. Specify **Task**, **Expected Outcomes**,
and **Constraints**: the outcome, evidence-based finish line, material decisions,
and delivery boundary. Persistence supplies no new scope or authority. Reconcile
current work and approvals before proposing the next useful outcome.

Brief supports read-only focus; Track records state; the owning execution
context and engineering methods perform research, review, and approved work.
Bounded subagents may help; Orchestrate remains the distinct authorized route
for sequential project-owned chat dispatch, not a parallel-team manager.

A separately authorized [scheduled follow-up](https://learn.chatgpt.com/docs/automations)
may wake the same chat under verified host capabilities. Notify on meaningful
change, completion, failure, or a needed decision; stay quiet while unchanged or
non-actionable. A wakeup supplies no consent and never resumes explicitly paused
work. This composition requires no new coordinator, runtime, or schedule.

## Signals and harnesses

A timer or supported event can supply a repository, resource link, revision or
run identity, and time. The caller's standing assignment supplies scope and
authority. A signal alone supplies neither. Stale or superseded signals may
produce a no-op; repeated signals reuse the same unfinished owning assignment.

Signal intake remains with the caller. Orchestrate receives affected owners and
assignments rather than scanning repositories for work. Periodic documentation
reconciliation and targeted repair can use the same maintenance skill. No event
receiver, polling service, or schedule is bundled.

Workflows keep harness mappings inside their owning skill. The
[Brief Codex mapping](../skills/brief/references/harnesses/codex.md) covers read-only
evidence; the [Orchestrate Codex adapter](../skills/orchestrate/references/harnesses/codex.md)
covers project/task discovery, inspection, creation, continuation, and waiting.
Another harness needs equivalent verified capabilities before dispatch can run.
