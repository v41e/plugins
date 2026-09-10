# Documentation Mode

## Input

Require an authorized documentation scope. Use repository ownership guidance
to identify the canonical documentation and any source generator that owns it.

## Workflow

1. Confirm the requested scope and inspect any active PR or task that already
   owns it.
2. Use relevant history, diffs, and targeted searches to connect source changes
   with their owning canonical docs.
3. Read current code, commands, manifests, tests, approved architecture, and
   repository guidance that directly define each selected surface.
4. Update only affected canonical docs; edit their generator when applicable.
5. Run applicable documentation, link, manifest, generator, and formatting
   checks. Do not reformat unrelated text.
6. Deliver through the permitted Git and PR workflow. If all selected surfaces
   are aligned, report a verified no-op.

## Output

Report the target and surface, evidence used, changed files or verified no-op,
validation, delivery state, coordination findings, and unresolved decisions.

## Rules

- A draft idea is not documentation drift.
- Add missing owned documentation when the authorized scope requires it.
- Inspect domain documentation only when scope and ownership put it in bounds.
- Report discrepancies outside the authorized execution context as coordination
  findings; do not edit them.
- Do not create speculative docs.
- Keep changes to documentation or its owning generator.
