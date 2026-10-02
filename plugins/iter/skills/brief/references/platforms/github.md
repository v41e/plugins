# GitHub Adapter

Current open work includes quiet pending reviews. Tracker status does not
establish goals or approvals.

## Evidence mapping

| When | Capability | Result |
| ---- | ---------- | ------ |
| Repository identity is unresolved | `gh repo view SOURCE --json nameWithOwner,url,defaultBranchRef` | Resolve `SOURCE` to a repository URL or `OWNER/REPO` from project links or local remotes; use the verified `OWNER/REPO` below. |
| Current backlog is relevant | `gh issue list --repo OWNER/REPO --state open --limit 1000 --json number,title,state,labels,assignees,createdAt,updatedAt,url`; fallback `gh api --paginate -X GET 'repos/OWNER/REPO/issues?state=open&per_page=100'` | Observe open Issues outside historical bounds. REST `/issues` includes PRs; remove entries containing `pull_request`. A capped result is **Partial**. |
| Current delivery or CI state is relevant | Compact command below; fallback `gh api --paginate -X GET 'repos/OWNER/REPO/pulls?state=open&per_page=100'` | Observe open PRs, compact check states/counts, and linked Issue identities outside historical bounds. Check changes need not change `updatedAt`. Empty checks do not establish success; capped results or REST fallback without these signals are **Partial**. |
| A selected conclusion needs contract, approval, review, or verification detail | `gh issue view NUMBER --repo OWNER/REPO --json number,title,state,body,labels,assignees,comments,projectItems,createdAt,updatedAt,closedAt,url`; `gh pr view NUMBER --repo OWNER/REPO --json number,title,state,body,isDraft,reviewDecision,reviews,comments,statusCheckRollup,closingIssuesReferences,headRefName,headRefOid,createdAt,updatedAt,closedAt,mergedAt,url`; `gh run view RUN_ID --repo OWNER/REPO --json databaseId,workflowDatabaseId,workflowName,headBranch,headSha,status,conclusion,attempt,createdAt,updatedAt,jobs,url` | Use bodies, comments, and reviews for ownership and explicit approval. Missing comments prove nothing. |

Current PR discovery keeps check states/counts and Issue identities compact:

```sh
gh pr list --repo OWNER/REPO --state open --limit 1000 \
  --json number,title,state,isDraft,reviewDecision,statusCheckRollup,closingIssuesReferences,headRefName,headRefOid,createdAt,updatedAt,url \
  --jq 'map(.statusCheckRollup |= ([.[]? | (.conclusion | select(. != null and . != "")) // .state // .status // "UNKNOWN"] | group_by(.) | map({state: .[0], count: length})) | .closingIssuesReferences |= [.[]? | {number,url}])'
```

## Selective references

| When | Capability | Result |
| ---- | ---------- | ------ |
| `status`, `retrospective`, or `plan` with `lookback` | [History adapter](github/history.md) | Exact-window closure, integration, workflow-attempt, and release evidence |
| `plan` has a verified Project mapping | [Planning adapter](github/planning.md) | Current Project items and prioritization evidence |

## Coverage semantics

- Current open state is observed now, not reconstructed at a past `as_of`.
- Missing access, truncation, or incomplete discovery is **Unknown** or
  **Partial**, never success.
