# Codex Harness

Use the host's `codex_app` tools and live schemas. Create or continue project
tasks only after human-authorized dispatch.

| Capability | Tools and semantics |
| ---------- | ------------------- |
| Resolve saved projects | `list_projects`; use returned project identity, path, and host rather than an invented project name or directory. |
| Discover active work | `list_threads`; titles and summaries are discovery leads, not current repository truth or proof that no other task exists. |
| Inspect selected work | `read_thread`; select relevant turns and follow pagination when the requested window or an unresolved decision needs older evidence. |
| Discover archived work | `list_archived_threads` when the window or linked history includes archived tasks; archived evidence does not authorize resumption. |
| Create project work | `create_thread`; only after human-authorized dispatch. Use the exact saved project. Preserve requested settings through supported arguments and choose a worktree only when explicitly requested. |
| Resolve pending creation | `list_threads`, then `read_thread` when needed; a pending `clientThreadId` is not a usable `threadId`. Confirm project, host, and assignment before waiting or continuing. |
| Continue owned work | `send_message_to_thread`; require human authorization and an unfinished task matching both project and assignment. |
| Inspect or wait for progress | `wait_threads`; `timeoutMs: 0` gives a compact read-only snapshot. Orchestrate waits on its one dispatched task with returned host and cursor; timeouts and setup are not completion. |

Tool availability and discovery coverage vary by host. Missing or ambiguous
identity remains unresolved; partial discovery cannot establish absence. Do not
substitute local subagents or repository edits for project-owned dispatch.
