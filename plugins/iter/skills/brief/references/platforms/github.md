# GitHub Adapter

Shared GitHub brief mappings.

## Evidence mapping

| Evidence            | Command                                                                                                                                                                                                                                                                                                                                                                                                                                                             | Semantics                                                                                                                                                 |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Repository identity | `gh repo view SOURCE --json nameWithOwner,url,defaultBranchRef`                                                                                                                                                                                                                                                                                                                                                                                                            | Resolve `SOURCE` to a repository URL or `OWNER/REPO` from project links or local remotes; use the verified `OWNER/REPO` below.                                                                                      |
| Current Issues      | `gh issue list --repo OWNER/REPO --state open --limit 1000 --json number,title,state,labels,assignees,projectItems,createdAt,updatedAt,url`; fallback `gh api --paginate -X GET 'repos/OWNER/REPO/issues?state=open&per_page=100'`                                                                                                                                                                                                                                                    | Observe current backlog outside historical bounds. REST `/issues` includes PRs; remove entries containing `pull_request`. A capped result is **Partial**. |
| Current PRs         | `gh pr list --repo OWNER/REPO --state open --limit 1000 --json number,title,state,isDraft,reviewDecision,statusCheckRollup,closingIssuesReferences,headRefName,headRefOid,createdAt,updatedAt,url`; fallback `gh api --paginate -X GET 'repos/OWNER/REPO/pulls?state=open&per_page=100'`                                                                                                                                                                                              | Observe current review state outside historical bounds. A capped result is **Partial**.                                                                   |
| Selected details    | `gh issue view NUMBER --repo OWNER/REPO --json number,title,state,body,labels,assignees,comments,projectItems,createdAt,updatedAt,closedAt,url`; `gh pr view NUMBER --repo OWNER/REPO --json number,title,state,body,isDraft,reviewDecision,reviews,comments,statusCheckRollup,closingIssuesReferences,headRefName,headRefOid,createdAt,updatedAt,closedAt,mergedAt,url`; `gh run view RUN_ID --repo OWNER/REPO --json databaseId,workflowName,headBranch,headSha,status,conclusion,attempt,createdAt,updatedAt,jobs,url` | Use bodies, comments, and reviews for ownership and explicit approval. Missing comments prove nothing.                                                    |

## Selective references

| Condition                              | Read                              |
| -------------------------------------- | --------------------------------- |
| `status` or `retrospective`            | [history.md](github/history.md)   |
| `plan` with `lookback`                 | [history.md](github/history.md)   |
| `plan` with a verified Project mapping | [planning.md](github/planning.md) |

## Coverage semantics

- Current open state is observed now, not reconstructed at a past `as_of`.
- Missing access, truncation, or incomplete discovery is **Unknown** or
  **Partial**, never success.
