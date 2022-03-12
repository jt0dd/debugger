### Terminology

Dynamic Execution: The program makes a web request, potentially decodes the response (for example, steganography) then executes that data.

### Objectives

I have five work-flow objectives for approaching reverse engineering:

1. I want to visualize control flow, stack, and register state like popular reverse engineering tools.
2. I want that visualization to reflect Dynamic Execution state changes at run-time.
3. I want to view registers, heap, and stack as a program executes.
4. I do not want to manually place breakpoints, but rather use hooks (via emulation) to conditionally halt.
5. I want to, where applicable, automate exploitation with Python.

To elaborate on #4, which might not be obvious, with some use-cases:

- Hook all jumps with destination addresses that seem unusual (not the start address of any local or imported subroutine, nor loop). This would be an effective analysis option. against ROPing and dynamically executing code.
- Hook all subroutines which accept untrusted external input. This would be effective as part of taint analysis.
- Hook any subroutine calls which would make code executable (VirtualProtect, for example).

These and other conditional hooking objectives would be either impractical or require time-consuming manual breakpoint placement to achieve with popular reverse engineering and debugging tools (to the best of my knowledge).

### Problem

Popular reverse engineering tools support objectives #1, #3, and #5, but do not support objectives #2 & #4.

### Solution

The problem warrants the need for a new tool. However, with Captone, Unicorn, Keystone, and Ghidra Python libraries all of the required features exist. So this project will join them and introduce an optional UI to accomplish all of my reverse engineering work-flow objectives.
