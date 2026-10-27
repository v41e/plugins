# Triage

## Purpose

Track a confirmed defect, diagnosis, proposed correction, and execution
authority.

## Input

Observed behavior that may contradict an expectation, current direction, and any
existing Issue discussion or supporting evidence.

## Workflow

1. Use the existing Issue as the contract, or prepare a lightweight local draft
   for a newly discovered defect. Establish expected and observed behavior,
   reproduction, owner, diagnosis, and acceptance evidence.
2. Keep a human report untriaged until evidence confirms the defect. An
   agent-discovered failure may proceed with sufficient evidence.
3. Hand missing diagnosis, reproduction, or acceptance work to the execution
   context and record its returned evidence.
4. Record the proposed correction, proportional steps, existing scope/execution
   approval, separate publication scope, and unresolved material decisions.
   Reuse existing approval and discussion; contract Review owns the next
   decision. A settled low-risk fix needs no separate spec or plan.

## Output

Confirmed defect and diagnosis, proposed correction, acceptance evidence,
proportional steps, authorization, and any unresolved material decision.

## Rules

- Missing defect or acceptance evidence remains unresolved; do not invent a fix.
