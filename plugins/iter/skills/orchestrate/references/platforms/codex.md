# Codex

Use the `codex_app` MCP server. Follow live tool descriptions and schemas for
arguments, defaults, and response handling.

| Concept                                    | Tool                          |
| ------------------------------------------ | ----------------------------- |
| Resolve saved projects                     | `list_projects`               |
| Find existing tasks                        | `list_threads`                |
| Inspect task ownership and progress        | `read_thread`                 |
| Create a task                              | `create_thread`               |
| Resolve a created task after pending setup | `list_threads`, `read_thread` |
| Continue a task                            | `send_message_to_thread`      |
| Wait for a task                            | `wait_threads`                |
