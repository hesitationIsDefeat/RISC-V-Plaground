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

## Special Registers
| Name  | Purpose |
|-------|---------|
| pc    | Program Counter |
| f0-f31 | Floating-Point Registers |
| csr   | Control and Status Registers (various) |

---