# Refactoring studio — private working notes, no submission

## Baseline
**Command run**: `python check_refactoring.py`
**Result actually observed (or: not executed)**: 14 tests passed "... ok"

## Proposed structural change
**We will extract**: formatting customer report information.
The existing behavior we must preserve: Formatted customer information.

## After the change
**Files changed**: reporting.py
**Checks actually run and observed result**: 14 tests still passed "... ok" no
difference.
**One claim these checks do not establish**: These checks do not established
that nothing changed in the results, it just verifies that what's check did not
change.


## Design judgment
### Keep or revert the extraction? Why?
#### The original change
Keep, it makes it easier to locatje where formatting belongs, it can help in
future modification if it is necessary to change formatting.

Is it actually needed?

New tests will need to be created for the helper function

Helper function is only used once.

### What future work might become easier?
Changing formatting in the future will be easier.

### What new indirection or dependency did we introduce?


## Connection to the submitted assessment
**My recommendation was**: Condense authentication methods into one single
method.
**One behavior-preserving preparatory step could be**: Extract authentication
inot a helper function with the intended behavior without changing the behavior
yet.
**The separately implemented behavior change would be**: The behavior wouldn't
have to change yet, behavior would be maintained until it is fully time to
switch.
**Evidence still needed / no supported implementation connection**:
