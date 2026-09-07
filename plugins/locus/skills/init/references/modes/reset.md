# Reset Selected Documents

## Input

An explicit replacement request naming the selected documents, current evidence,
and the chosen target and templates.

## Workflow

1. Read the existing selected documents, target reference, and selected
   templates completely.
2. Verify replacement facts from current repository or destination evidence.
3. Report useful or uncertain content the replacement would discard; stop if
   the requested scope is ambiguous.
4. Replace only the named documents and leave every unselected file unchanged.
5. Reset optional architecture documentation only when it is explicitly named
   and the target contract permits it.

## Output

Report replaced documents, material discarded content, validation, and unresolved
facts under the parent skill's output contract.

## Rules

- Reset requires explicit replacement authorization for the named documents.
- Leave unselected documents unchanged.
