# Triage

## Purpose

Track a confirmed defect and the proportional design and plan for its fix.

## Input

Observed behavior that may contradict an expectation.

## Workflow

1. Record expected and observed behavior, reliable reproduction and supporting
   evidence, priority, owner, diagnosis, and acceptance evidence.
2. Keep a human report untriaged until evidence confirms the defect. An
   agent-discovered failure may proceed with sufficient evidence.
3. Hand missing diagnosis, reproduction, or acceptance work to the execution
   context and record its returned evidence.
4. For substantive fixes, apply [Design](design.md) then [Plan](plan.md) checkpoints
   inside Triage: independent final-spec review/corrections and summary before
   human spec approval, then independent plan review/corrections and summary before
   separate plan/execution approval. Record the stated delivery scope. Keep Bug
   classification; routine settled fixes stay direct unless policy requires gates.

## Output

Confirmed defect, acceptance evidence, and authorization, or the unmet gate.
Advance to Implement only when the gate is satisfied.

## Rules

- Missing defect or acceptance evidence blocks advancement; do not invent a fix.
