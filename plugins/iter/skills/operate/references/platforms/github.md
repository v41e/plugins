# GitHub Adapter

Shared GitHub mappings for ownership and authorization checks.

## Evidence mapping

| Evidence             | Command                                                                                                                                                                                                                                                                                                   | Semantics                                                                                                                                                          |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Identity and access  | `gh auth status`; `gh repo view SOURCE --json nameWithOwner,url,defaultBranchRef`                                                                                                                                                                                                                                | Resolve `SOURCE` from project links or local remotes; verify its URL or `OWNER/REPO`, host, and account. Authentication does not authorize work.                                                                  |
| Open PRs             | `gh pr list --repo OWNER/REPO --state open --limit 1000 --json number,title,isDraft,reviewDecision,statusCheckRollup,closingIssuesReferences,headRefName,headRefOid,createdAt,updatedAt,url`; fallback `gh api --paginate -X GET 'repos/OWNER/REPO/pulls?state=open&per_page=100'`                                          | Find existing ownership of the selected outcome. A capped result is **Partial**.                                                                                   |
| Selected Issue or PR | `gh issue view NUMBER --repo OWNER/REPO --json number,title,state,body,labels,assignees,comments,projectItems,createdAt,updatedAt,url`; `gh pr view NUMBER --repo OWNER/REPO --json number,title,state,body,isDraft,reviewDecision,reviews,comments,statusCheckRollup,closingIssuesReferences,headRefName,headRefOid,createdAt,updatedAt,url` | Use bodies, comments, and reviews for the work contract, ownership, approval, pauses, and restrictions. The latest human restriction wins; silence proves nothing. |

## Selective references

| Mode            | Read                                                                                   |
| --------------- | -------------------------------------------------------------------------------------- |
| `engineering`   | [engineering.md](github/engineering.md)                                                |
| `documentation` | No extra GitHub reference; use shared ownership rows and local documentation evidence. |

## Boundary semantics

- Evidence collection is read-only. Writes require explicit authorization and
  repository policy.
- Missing, capped, or inaccessible evidence is **Partial** or **Unknown**.
