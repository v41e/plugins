# GitHub Planning Adapter

## Evidence mapping

| When | Capability | Result |
| ---- | ---------- | ------ |
| Planning guidance identifies a Project | `gh project list --owner OWNER --limit 1000 --format json` | Resolve the current title-to-number mapping; never use a remembered number. |
| The Project identity is resolved | `gh project item-list NUMBER --owner OWNER --limit 1000 --format json` | Keep exact `OWNER/REPO` items. A draft needs an explicit repository link or mapping. Status does not prove approval or commitment. |

Combine Project items with current Issue and PR evidence from the root adapter;
do not query future events inside the planning horizon.
