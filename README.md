# VHDL Counter Overflow Bug

This repository demonstrates a common but subtle bug in VHDL code: an integer overflow in a counter when the clock frequency is very high. The `buggy_counter.vhdl` file shows the buggy code.  The `fixed_counter.vhdl` provides a corrected version that prevents the issue.

## Bug Description
The original counter's `internal_count` signal can overflow if the clock cycle is shorter than the time taken to increment the counter. This can lead to skipped values and unpredictable behavior. 

## Solution
The solution employs a more robust approach by ensuring that the counter only updates reliably during each rising clock edge. In the fix, more careful consideration is given to the timing of the update.

## How to reproduce the bug
1. Synthesize the buggy code and implement it in hardware.
2. Increase the clock frequency significantly.
3. Observe that the counter may skip values or display unexpected behavior.

## How to run the solution
Synthesize the fixed counter code and implement it in hardware. The improved implementation should correctly count up to 15 before resetting.