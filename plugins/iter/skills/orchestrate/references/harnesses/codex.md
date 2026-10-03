# Codex Harness

Use the host's `codex_app` tools and live schemas.

| When | Capability | Result |
| ---- | ---------- | ------ |
| Resolving requested owners | `list_projects` | Exact saved project identity, path, and host |
| Finding existing assignments | `list_threads` | Discovery leads; titles and summaries do not prove assignment identity or absence |
| Verifying a selected assignment | `read_thread` | Relevant turns; pagination when older decisions or the requested window require it |
| Linked history includes archived work | `list_archived_threads` | Historical evidence; resumption still needs authorization |
| Authorized dispatch has no matching unfinished task | `create_thread` | Work in the exact saved project; pass requested settings through supported arguments; a worktree needs an explicit request |
| Creation is pending | `list_threads`, then `read_thread` as needed | Confirmed project, host, assignment, and usable `threadId`; a `clientThreadId` cannot be used for waiting or continuation |
| Authorized continuation matches unfinished project and assignment | `send_message_to_thread` | Continuation of that assignment |
| Collecting the dispatched task's outcome | `wait_threads` | Progress using its returned host and cursor; setup and timeouts are not completion; `timeoutMs: 0` provides a snapshot |

Availability and discovery coverage vary by host. Unresolved identity or partial
discovery cannot establish that a matching task is absent.
