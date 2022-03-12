### Terminology

Dynamic Execution: The program makes a web request, decodes data (for example, steganography) then executes that data.

### Objective

I have four work-flow objectives for approaching reverse engineering:

- I want to visualize control flow, stack, and register state like Ghidra / IDA.
- I want that visualization to reflect Dynamic Execution state changes at run-time.
- I want to view registers, heap, and stack as a program executes.
- I do not want to manually place breakpoints, but rather use hooks (via emulation) to conditionally halt.
- I want to, where applicable, automate exploitation with Python.
