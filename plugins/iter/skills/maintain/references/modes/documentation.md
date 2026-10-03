# Documentation Reconciliation

## Purpose

Reconcile owned documentation with verified current behavior and approved intent.

## Input

Authorized documentation scope, audience and purpose, current canonical sources,
and generators owning the selected surfaces.

## Workflow

Verify a concrete discrepancy against code, commands, manifests, tests, or
approved decisions. Use installed `locus:write` for content placement and
reconciliation; otherwise update the nearest owned source directly. Correct,
consolidate, or remove superseded text. Edit the generator when it owns output,
then regenerate. Validate affected facts, links, examples, commands, and required
checks. Report a verified no-op when the surfaces already serve their purpose.

## Output

Corrections and verification, with remaining knowledge gaps or decisions linked
to their owners.

## Rules

- Change only authorized documentation or its owning generator.
- Draft ideas are not documentation drift. Preserve the difference between
  implemented behavior, approved intent, and proposals.
