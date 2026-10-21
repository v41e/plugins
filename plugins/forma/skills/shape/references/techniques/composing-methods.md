# Composing Methods

## Extract Method

[Source](https://refactoring.guru/extract-method)

### Problem

A coherent operation is buried inside a larger method.

### Solution

- Extract → name the operation and replace the fragment with a call.
- Inputs → pass outer values; keep variables used only inside the fragment
  local.
- Outputs → return changed values needed later; preserve evaluation order,
  exits, and effects.

## Inline Method

[Source](https://refactoring.guru/inline-method)

### Problem

A method's body explains its purpose better than its name.

### Solution

- Check eligibility → keep methods overridden by subclasses and preserve
  supported public boundaries.
- Replace calls → substitute the body, preserving argument evaluation, receiver
  state, and return paths.
- Finish → remove the method only after every caller has migrated.

## Extract Variable

[Source](https://refactoring.guru/extract-variable)

### Problem

A complex expression hides its conditions or intermediate calculations.

### Solution

- Name a part → assign the expression to a descriptive local and replace that
  occurrence.
- Conditional work → preserve short circuit evaluation; do not eagerly compute
  previously skipped branches.
- Repeated logic → consider [Extract Method](#extract-method); avoid locals that
  merely restate syntax.

## Inline Temp

[Source](https://refactoring.guru/inline-temp)

### Problem

A temporary only forwards a simple expression without useful meaning.

### Solution

- Check its role → retain intentional snapshots and caches of expensive
  calculations.
- Inline → substitute the expression at each use, preserving evaluation timing
  and side effects.
- Finish → remove the assignment and declaration; abandon the change if repeated
  evaluation costs outweigh clarity.

## Replace Temp with Query

[Source](https://refactoring.guru/replace-temp-with-query)

### Problem

A local calculation obstructs extraction or duplicates reusable logic.

### Solution

- Multiple assignments → [split the temporary](#split-temporary-variable) so
  each value is assigned once.
- Extract the calculation → return its result from a new method and replace
  variable uses with calls to it.
- Calculation changes visible state →
  [separate query from modification](method-calls.md#separate-query-from-modifier)
  before replacing uses.
- Repeated calls → preserve evaluation semantics; retain a cached result for
  expensive work or required snapshots.

## Split Temporary Variable

[Source](https://refactoring.guru/split-temporary-variable)

### Problem

One local variable represents unrelated values during a method.

### Solution

- First responsibility → rename its assignment and uses up to the next unrelated
  assignment.
- Later responsibilities → repeat with distinct, meaningful names while
  preserving the values each branch uses.
- Intentional accumulation → retain loop counters and accumulators whose
  changing value serves one role.

## Remove Assignments to Parameters

[Source](https://refactoring.guru/remove-assignments-to-parameters)

### Problem

Reassigning an input parameter obscures the original argument's meaning.

### Solution

- Create a working value → initialize a local from the parameter before
  reassignment.
- Redirect subsequent work → use the local while preserving access to the
  original input.
- Shared references → distinguish reassigning the parameter from changing its
  object; preserve intentional outputs to the caller.

## Replace Method with Method Object

[Source](https://refactoring.guru/replace-method-with-method-object)

### Problem

Interdependent locals prevent useful extraction from a long method.

### Solution

- Choose only when needed → ordinary [Extract Method](#extract-method) avoids an
  additional class.
- Build a calculation object → move the method body into a class and its locals
  into fields; initialize inputs and retain the original receiver when needed.
- Delegate each invocation → create fresh state, run the calculation, then
  extract smaller methods inside it.

## Substitute Algorithm

[Source](https://refactoring.guru/substitute-algorithm)

### Problem

An existing algorithm can be replaced by a clearer or more efficient one.

### Solution

- Isolate first → extract unrelated work and implement the replacement behind
  the same contract.
- Existing library or framework operation fits → use it instead of maintaining a
  custom algorithm.
- Compare before deleting → retain the old implementation while checking
  representative and boundary cases.
- Establish equivalence → preserve results, ordering, duplicates, precision,
  effects, errors, and resource limits; investigate mismatches.
