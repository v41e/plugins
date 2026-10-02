# GitHub History Adapter

## Evidence mapping

| When | Capability | Result |
| ---- | ---------- | ------ |
| Issue closure evidence is relevant to the window | `gh issue list --repo OWNER/REPO --state closed --search 'closed:START_DATE..END_DATE' --limit 1000 --json number,title,state,closedAt,createdAt,updatedAt,url`; fallback `gh api --paginate -X GET 'repos/OWNER/REPO/issues?state=closed&per_page=100'` | Date search finds candidates. Retain `closedAt` inside exact `[start, end)`. REST Issues include PRs; remove entries containing `pull_request`. A reopened Issue needs `gh api --paginate -X GET 'repos/OWNER/REPO/issues/NUMBER/timeline?per_page=100'` when closure-event fidelity matters; otherwise event coverage is **Partial**. |
| Integration evidence is relevant to the window | `gh pr list --repo OWNER/REPO --state merged --search 'merged:START_DATE..END_DATE' --limit 1000 --json number,title,state,mergedAt,closedAt,createdAt,updatedAt,url`; fallback `gh api --paginate -X GET 'repos/OWNER/REPO/pulls?state=closed&per_page=100'` | Date search finds candidates. Retain `mergedAt` inside exact `[start, end)`. |
| CI outcomes or reruns are relevant to the window | `gh run list --repo OWNER/REPO --created 'START_DATE..END_DATE' --limit 1000 --json databaseId,workflowDatabaseId,workflowName,displayTitle,headBranch,headSha,event,status,conclusion,attempt,createdAt,updatedAt,url`; `gh run list --repo OWNER/REPO --commit HEAD_SHA --limit 100 --json databaseId,workflowDatabaseId,workflowName,headBranch,headSha,status,conclusion,attempt,createdAt,updatedAt,url`; `gh api repos/OWNER/REPO/actions/runs/RUN_ID/attempts/ATTEMPT` | Created-time search misses reruns. Reconcile attempts by stable workflow ID, branch, and commit. Incomplete rerun discovery is **Partial**. |
| Published release evidence is relevant to the window | `gh api --paginate -X GET 'repos/OWNER/REPO/releases?per_page=100'` | Retain non-drafts with non-null `published_at` inside exact `[start, end)`. Label prereleases; never infer deployment. |

## Coverage semantics

- Apply exact UTC half-open bounds after broad date discovery.
- Use selected-detail commands from the root adapter after discovery.
- Historical evidence requires an established window; a `plan` without lookback
  has no historical query.
