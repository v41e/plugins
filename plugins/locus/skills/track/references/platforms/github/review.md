# Review

GitHub actions for the Locus Review phase.

## Actions

- Complete the Review phase's required local checkpoint and delivery authority
  check before creating or updating the pull request.
- Create or update the pull request and move its Project item to the mapped
  review state.
- Follow the repository pull-request template when present. Otherwise include a
  related-Issue link, `Summary`, `Verification`, and material `Notes`.
- When the pull request targets a non-default branch, link its Issue manually;
  closing keywords create no link and do not auto-close it.
- Collect remote checks and reviews for the exact pull-request head. Report green
  CI only as evidence for the checks it ran, not as proof of unperformed local,
  browser, or manual validation.

## Boundaries

- Keep the delivery record open while requested changes return to Implement.
- Do not close the Issue or mark the Project item done before authorized
  integration.
