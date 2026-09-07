# Create Missing Documents

## Input

Selected missing documents, verified facts, and the chosen target and templates.

## Workflow

1. Confirm the selected paths do not exist.
2. Read the target reference and only the templates for the selected documents.
3. Create only those documents, using verified facts and the target contract.
4. Follow target-specific conditions; for example, do not create optional
   architecture documentation merely because a template exists.

## Output

Report created documents, validation, and unresolved facts under the parent
skill's output contract.

## Rules

- Use Create only when every selected document is absent; otherwise use Refresh.
