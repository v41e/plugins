# GitHub Adapter

## Capability resolution

Before a tracking mutation, inspect only the repository, organization, and
owning Project metadata needed for it. Map a logical concept only when a rename,
description, policy, automation, or one-to-one meaning establishes equivalence.
Record `logical -> existing [GitHub surface] (evidence)`. Record unmapped
concepts, omit their mutations, and report them; a plausible or sole ambiguous
candidate is insufficient. Never create, rename, disable, or delete GitHub
configuration.

## Surfaces

| Logical concept | GitHub surface |
| --------------- | -------------- |
| Backlog record | Project draft |
| Formal work record | Issue |
| Approved specification or plan snapshot | Separate Issue comment |
| Ready, active, review, done | Mapped Project status |
| Delivery record | Existing pull request supplied by the delivery owner |

## Synchronization

| Gate | Authorized tracking actions |
| ---- | --------------------------- |
| Ideate | Create or consolidate one resumable Feature draft in the mapped backlog state when an owning Project and mapping exist; link any local draft. Set title, body, real assignees, and mapped Project fields; defer repository, Issue Type, labels, milestone, organization Issue fields, and Issue relationships until conversion. Otherwise leave GitHub unchanged. |
| Design | Once settled and required approvals are satisfied, promote the linked draft or create a Feature Issue only when a repository contract is required. Publish an approved local specification as a separate comment. |
| Plan | Publish the approved local plan as a separate Issue comment; synchronize mapped ready state and refresh mapped Priority/Effort. |
| Triage | Create or update a Bug Issue only when policy, human intent, or existing tracking requires it. Record the current triage evidence; publish any approved local design or plan separately. Never create a Bug Project draft. |
| Scope | Continue an existing Task record unless policy or human intent says otherwise; create a Task Issue only when a formal contract is required. Publish any approved local design or plan separately. |
| Implement | Synchronize mapped active state and mapped Start Date when implementation actually begins. |
| Review | Record the existing PR and synchronize the work item's mapped review state. Verify required local checkpoint and delivery authority from supplied evidence. Link its Issue manually when the PR targets a non-default branch: closing keywords create neither a link nor automatic closure there. Collect remote checks and reviews for the exact PR head. Keep delivery open during corrections. |
| Complete | After authorized integration, verify linked Issues are closed and Project items use mapped done state; correct only authorized state. Non-default-target Issue references or manual links may still need explicit closure. |

## Issue contracts

Follow repository Issue Forms when present. Otherwise:

| Work | Initial Issue body |
| ---- | ------------------ |
| Feature / Task | `Problem`, `Solution`, optional `Alternatives`, optional `Context` |
| Bug | `Description`, `Current behavior`, `Expected behavior`, `Reproduction`, optional `Environment`, `Logs`, `Possible fix` |

Omit empty optional sections. Keep Issue/Project tracking URLs, stage, Project
fields, local Tracking metadata, specification/design, and plan out of the
initial body. Approved snapshots are separate comments with local-only tracking
metadata removed.

Apply mapped Issue Type or repository label and understood mapped Priority and
Effort. Assign people or relationships only when real. Target Date represents a
real scheduling commitment; a milestone represents a concrete release or dated
target. Remove intake-only labels after acceptance; preserve orthogonal labels.

For an existing PR, record related Issues, summary, verification, and material
notes using its template when present. PR creation and delivery mutations belong
to the delivery owner. Green CI proves only the checks it ran, not unperformed
local, browser, or manual validation.

## Rules

- Follow the selected lifecycle's order and gates. Synchronize only when policy,
  human direction, or existing owned records require it; an explicit opt-out
  wins. Without that condition, leave GitHub unchanged.
- Projects and structured metadata are optional; an Issue may exist without
  either. Skip actions whose record, item, field, or mapping is absent.
- Track does not create pull requests or perform the delivery owner's
  engineering work. Close Issues or mark work done only after authorized
  integration.

GitHub's [Issue linking rules](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue)
own closing-keyword and branch-target semantics.
