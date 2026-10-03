# Codex Evidence Mapping

Use the host's `codex_app` tools and live schemas for read-only evidence.

| When | Capability | Result |
| ---- | ---------- | ------ |
| Requested saved projects need resolution | `list_projects` | Returned identities, paths, and hosts resolve the requested scope. |
| Active work discovery is relevant | `list_threads` | Titles and summaries are discovery leads, not current repository truth. Partial discovery cannot establish absence. |
| Selected work needs decision or historical evidence | `read_thread` | Relevant turns, with pagination when the requested window or unresolved decision needs older evidence. |
| The window or linked history includes archived work | `list_archived_threads` | Archived evidence without authorization to resume it. |
| Selected work needs current progress evidence | `wait_threads` with `timeoutMs: 0` | Compact read-only snapshot; setup and timeouts do not establish completion. |

Record missing or ambiguous identities and incomplete discovery as coverage gaps.
Brief does not create, continue, change, or archive tasks. Supplied local evidence
remains usable without Codex tools.
