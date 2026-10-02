# GitHub Evidence Mappings

Use only the capabilities needed for the selected maintenance scope. Start with
compact discovery, then inspect selected records and histories.

| Evidence | Capability | Meaning |
| -------- | ---------- | ------- |
| Repository and account | `gh auth status`; `gh repo view SOURCE --json nameWithOwner,url,defaultBranchRef` | Resolve `SOURCE` from project links or local remotes. Verify host, exact repository and account; authentication is not authority. |
| Existing PR ownership | `gh pr list --repo OWNER/REPO --state open --limit 1000 --json number,title,isDraft,headRefName,headRefOid,updatedAt,url`; paginated fallback: `gh api --paginate -X GET 'repos/OWNER/REPO/pulls?state=open&per_page=100'` | Locate work already owned by another active assignment; open or draft state alone does not identify its authorization or executor. |
| Selected work contract | `gh issue view NUMBER --repo OWNER/REPO --json number,title,state,body,labels,assignees,comments,projectItems,updatedAt,url`; `gh pr view NUMBER --repo OWNER/REPO --json number,title,state,body,isDraft,reviewDecision,reviews,comments,statusCheckRollup,closingIssuesReferences,headRefName,headRefOid,updatedAt,url` | Read the selected contract and human decisions. Reconcile task ownership, approval, pauses, and restrictions; the latest human restriction wins. |
| Engineering candidates | `gh issue list --repo OWNER/REPO --state open --limit 1000 --json number,title,labels,assignees,projectItems,updatedAt,url`; paginated fallback: `gh api --paginate -X GET 'repos/OWNER/REPO/issues?state=open&per_page=100'` | Discovery is evidence, not the maintenance agenda. REST `/issues` includes PRs; exclude entries containing `pull_request`. |
| CI discovery and diagnosis | `gh run list --repo OWNER/REPO --limit 1000 --json databaseId,workflowDatabaseId,headBranch,headSha,status,conclusion,attempt,updatedAt,url`; `gh run list --repo OWNER/REPO --commit HEAD_SHA --limit 100 --json databaseId,workflowDatabaseId,headBranch,headSha,status,conclusion,attempt,updatedAt,url`; `gh run view RUN_ID --repo OWNER/REPO --json databaseId,workflowDatabaseId,headBranch,headSha,status,conclusion,attempt,updatedAt,jobs,url`; `gh run view RUN_ID --repo OWNER/REPO --log-failed`; `gh api repos/OWNER/REPO/actions/runs/RUN_ID/attempts/ATTEMPT` | Load selected failed logs for diagnosis. Supersede a failure only with newer success for the same stable workflow ID, branch, and commit. Recent runs alone do not prove full rerun coverage. |
| Optional project records | `gh project list --owner OWNER --limit 1000 --format json`; `gh project item-list NUMBER --owner OWNER --limit 1000 --format json` | Resolve live title-to-number mappings. Keep exact repository items; drafts require an explicit repository link or mapping. Project status does not establish approval. |

Evidence collection is read-only. A capped, missing, or inaccessible result is
**Partial** or **Unknown**. Tracking writes belong to authorized tracking;
delivery writes belong to the owning context's separate delivery grants.
