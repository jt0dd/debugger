### Terminology

Dynamic Execution: The program makes a web request, potentially decodes the response (for example, steganography) then executes that data.

### Objectives

I have five work-flow objectives for approaching reverse engineering:

1. I want to visualize control flow, stack, and register state like popular reverse engineering tools.
2. I want that visualization to reflect Dynamic Execution state changes at run-time.
3. I want to view registers, heap, and stack as a program executes.
4. I do not want to manually place breakpoints, but rather use hooks (via emulation) to conditionally halt.
5. I want to, where applicable, automate exploitation with Python.

### Problem

Popular reverse engineering tools support objectives #1, #3, and #5, but do not support objectives #2 & #4.

### Solution

The problem warrants the need for a new tool. However, with Captone, Unicorn, Keystone, and Ghidra Python libraries all of the required features exist. So this project will join them and introduce an optional UI to accomplish all of my reverse engineering work-flow objectives.
