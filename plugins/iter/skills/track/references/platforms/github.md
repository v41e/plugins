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

| When | Capability | Result |
| ---- | ---------- | ------ |
| A resumable Feature lacks a formal contract and has an owning Project and backlog mapping | Project draft | Consolidate one draft and link any local draft. Set title, body, real assignees, and mapped Project fields; defer repository, Issue Type, labels, milestone, organization Issue fields, and relationships until conversion. |
| A Feature design is settled, required approvals hold, and a repository contract is required | Feature Issue | Promote its linked draft or create the formal contract. |
| A Bug requires tracking by policy, human intent, or existing records | Bug Issue | Create or update its triage evidence; never create a Bug Project draft. |
| A Task already has a record or requires a formal repository contract | Task record or Issue | Reuse the record unless policy or human intent says otherwise; create an Issue only when a formal contract is required. |
| An approved local specification/design or plan has an owning Issue | Separate Issue comments | Publish each approved snapshot separately, with local-only tracking metadata removed. |
| The selected workflow is ready for implementation | Mapped ready status and Priority/Effort | Synchronize ready state and understood priority/effort after required gates. |
| Implementation actually begins | Mapped active status and Start Date | Record actual start; stage names alone do not establish execution. |
| The delivery owner supplies an existing PR for review | Existing PR and mapped review status | Record its identity, required local checkpoint, and delivery authority from supplied evidence; collect checks and reviews for its exact head. Keep delivery open during corrections. |
| The PR targets a non-default branch | Manual Issue link | Link its Issue explicitly; closing keywords create neither the link nor automatic closure. |
| Authorized integration and completion verification are established | Linked Issue and mapped done status | Verify closure and done state; correct only authorized state. Non-default-target links or references may need explicit Issue closure. |

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
  integration and completion verification.
- Automatic merge eligibility follows a separate policy decision; PR types and
  green checks alone do not establish it.

GitHub's [Issue linking rules](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue)
own closing-keyword and branch-target semantics.
