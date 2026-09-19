# Plan

## Input

The Feature design is settled and any required design approval is satisfied.

## Workflow

1. Define owners, files, checks, and boundaries at proportional depth.
2. Keep bounded, low-risk steps inline. Otherwise write one short executable
   plan for multi-step or handed-off work.
3. Reuse execution authorization for settled steps; obtain separate plan approval
   only when human intent or repository policy requires it.
4. When a formal remote record exists, publish the approved local plan without
   local-only tracking metadata.
5. Refresh mapped metadata and move any remote tracked item to ready.

## Output

Return the plan for a planning-only request. Otherwise continue to Implement
when execution is authorized, or report the settled steps and remaining gate.

## Rules

- Continue in the current task or hand off only the approved design and
  implementation steps to a separate execution task.
