# Codex Evidence Mapping

Use the host's `codex_app` tools and live schemas for read-only evidence.

| Capability | Tools and semantics |
| ---------- | ------------------- |
| Resolve saved projects | `list_projects`; use returned identities, paths, and hosts to resolve the requested scope. |
| Discover active work | `list_threads`; titles and summaries are discovery leads, not current repository truth. Partial discovery cannot establish absence. |
| Inspect selected work | `read_thread`; select relevant turns and follow pagination when the requested window or an unresolved decision needs older evidence. |
| Discover archived work | `list_archived_threads` when the window or linked history includes archived tasks. Archived evidence does not authorize resumption. |
| Inspect progress | `wait_threads` with `timeoutMs: 0` for a compact read-only snapshot; setup and timeouts do not establish completion. |

Record missing or ambiguous identities and incomplete discovery as coverage gaps.
Brief does not create, continue, change, or archive tasks. Supplied local evidence
remains usable without Codex tools.
