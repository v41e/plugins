# Triage

## Input

Observed behavior that may contradict an expectation.

## Workflow

1. Record expected and observed behavior, reliable reproduction and supporting
   evidence, priority, owner, diagnosis, and acceptance evidence.
2. Keep a human report untriaged until evidence confirms the defect. An
   agent-discovered failure may proceed with sufficient evidence.
3. Hand missing diagnosis, reproduction, or acceptance work to the execution
   context and record its returned evidence.

## Output

Confirmed defect and acceptance evidence, or the missing evidence. Advance to
Implement only when the gate is satisfied.

## Rules

- Missing defect or acceptance evidence blocks advancement; do not invent a fix.
