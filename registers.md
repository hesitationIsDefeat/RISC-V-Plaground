# RISC-V Registers

This document lists the general-purpose and special-purpose registers in RISC-V.

## General-Purpose Registers (GPRs)
| Name  | Alias | Purpose |
|-------|-------|---------|
| x0    | zero  | Hardwired to 0 |
| x1    | ra    | Return address |
| x2    | sp    | Stack pointer |
| x3    | gp    | Global pointer |
| x4    | tp    | Thread pointer |
| x5    | t0    | Temporary register 0 |
| x6    | t1    | Temporary register 1 |
| x7    | t2    | Temporary register 2 |
| x8    | s0/fp | Saved register 0 / Frame pointer |
| x9    | s1    | Saved register 1 |
| x10   | a0    | Function argument 0 / Return value |
| x11   | a1    | Function argument 1 / Return value |
| x12   | a2    | Function argument 2 |
| x13   | a3    | Function argument 3 |
| x14   | a4    | Function argument 4 |
| x15   | a5    | Function argument 5 |
| x16   | a6    | Function argument 6 |
| x17   | a7    | Function argument 7 |
| x18   | s2    | Saved register 2 |
| x19   | s3    | Saved register 3 |
| x20   | s4    | Saved register 4 |
| x21   | s5    | Saved register 5 |
| x22   | s6    | Saved register 6 |
| x23   | s7    | Saved register 7 |
| x24   | s8    | Saved register 8 |
| x25   | s9    | Saved register 9 |
| x26   | s10   | Saved register 10 |
| x27   | s11   | Saved register 11 |
| x28   | t3    | Temporary register 3 |
| x29   | t4    | Temporary register 4 |
| x30   | t5    | Temporary register 5 |
| x31   | t6    | Temporary register 6 |

### In Depth Explanations
| Alias | Explanation |
|-------|------------|
| zero  | Contains the value 0 all the time. Can be used in the process of loading an immediate value to another register or can be used as the return register to discard an unwanted value. |
| ra    | Holds the return address that will be returned to after the execution of the called function ends. |
| sp    | Holds the end address of the stack memory. Allows allocating stack memory and reading from it. |
| gp    | Holds the start address of Small Data Section or Small BSS Section, where frequently accessed global or static data are stored. Used to access these data by offsets. |
| tp    | Holds the start address of Thread Control Block or Thread-Local Storage for a given thread. Thread-specific data is stored here. Used to access these data by offsets. |
| fp/s0 | Used as a frame pointer to help with accessing local variables in stack frames when debugging or when stack frames are not optimized away. |
| t(i)  | Can be used to store temporary values. Caller-saved. |

**Caller-saved**: Any value in it must be stored before calling a function, if the value is required to stay the same after the function ends.

**Callee-saved**: Any value in it must be stored inside of the called function, if the value is required to stay the same after the function ends.

## Special Registers
| Name  | Purpose |
|-------|---------|
| pc    | Program Counter |
| f0-f31 | Floating-Point Registers |
| csr   | Control and Status Registers (various) |

### In Depth Explanations
| Name  | Explanation |
|-------|------------|
| pc    | The Program Counter (PC) holds the memory address of the next instruction to be executed. It increments automatically after each instruction fetch unless modified by a jump or branch instruction. |
| f0-f31 | These are 32 floating-point registers used for floating-point arithmetic operations. They store single-precision (32-bit) and double-precision (64-bit) floating-point values depending on the floating-point extension of the RISC-V ISA. |
| csr   | Control and Status Registers (CSR) store various system control and status information, including privilege levels, exception handling, and performance monitoring. Some common CSR registers include `mstatus` (machine status), `mtvec` (machine trap-vector base address), and `mepc` (machine exception program counter). |

---

