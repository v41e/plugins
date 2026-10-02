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

## Historical evidence

| When | Capability | Result |
| ---- | ---------- | ------ |
| Issue closure evidence is relevant to the window | `gh issue list --repo OWNER/REPO --state closed --search 'closed:START_DATE..END_DATE' --limit 1000 --json number,title,state,closedAt,createdAt,updatedAt,url`; fallback `gh api --paginate -X GET 'repos/OWNER/REPO/issues?state=closed&per_page=100'` | Date search finds candidates. Retain `closedAt` inside exact `[start, end)`. REST Issues include PRs; remove entries containing `pull_request`. A reopened Issue needs `gh api --paginate -X GET 'repos/OWNER/REPO/issues/NUMBER/timeline?per_page=100'` when closure-event fidelity matters; otherwise event coverage is **Partial**. |
| Integration evidence is relevant to the window | `gh pr list --repo OWNER/REPO --state merged --search 'merged:START_DATE..END_DATE' --limit 1000 --json number,title,state,mergedAt,closedAt,createdAt,updatedAt,url`; fallback `gh api --paginate -X GET 'repos/OWNER/REPO/pulls?state=closed&per_page=100'` | Date search finds candidates. Retain `mergedAt` inside exact `[start, end)`. |
| CI outcomes or reruns are relevant to the window | `gh run list --repo OWNER/REPO --created 'START_DATE..END_DATE' --limit 1000 --json databaseId,workflowDatabaseId,workflowName,displayTitle,headBranch,headSha,event,status,conclusion,attempt,createdAt,updatedAt,url`; `gh run list --repo OWNER/REPO --commit HEAD_SHA --limit 100 --json databaseId,workflowDatabaseId,workflowName,headBranch,headSha,status,conclusion,attempt,createdAt,updatedAt,url`; `gh api repos/OWNER/REPO/actions/runs/RUN_ID/attempts/ATTEMPT` | Created-time search misses reruns. Reconcile attempts by stable workflow ID, branch, and commit. Incomplete rerun discovery is **Partial**. |
| Published release evidence is relevant to the window | `gh api --paginate -X GET 'repos/OWNER/REPO/releases?per_page=100'` | Retain non-drafts with non-null `published_at` inside exact `[start, end)`. Label prereleases; never infer deployment. |

## Planning evidence

| When | Capability | Result |
| ---- | ---------- | ------ |
| Planning guidance identifies a Project | `gh project list --owner OWNER --limit 1000 --format json` | Resolve the current title-to-number mapping; never use a remembered number. |
| The Project identity is resolved | `gh project item-list NUMBER --owner OWNER --limit 1000 --format json` | Keep exact `OWNER/REPO` items. A draft needs an explicit repository link or mapping. Status does not prove approval or commitment. |

Combine Project items with current Issue and PR evidence above; do not query
future events inside the planning horizon.

## Coverage semantics

- Current open state is observed now, not reconstructed at a past `as_of`.
- Apply exact UTC half-open bounds after broad date discovery; use the selected
  detail commands above when needed.
- Historical evidence requires an established window; a `plan` without lookback
  has no historical query.
- Missing access, truncation, or incomplete discovery is **Unknown** or
  **Partial**, never success.
