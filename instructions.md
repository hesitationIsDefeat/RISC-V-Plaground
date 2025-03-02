# RISC-V Instruction Types

RISC-V instructions are categorized into different types based on their format and function. These instruction types define how the opcode, registers, and immediate values are arranged within a 32-bit or compressed 16-bit instruction.

## Instruction Types

| Type | Description |
|------|-------------|
| R-Type | Register-to-register operations, such as addition and bitwise operations. |
| I-Type | Immediate-based operations, including arithmetic and load instructions. |
| S-Type | Store instructions, which save data from a register into memory. |
| B-Type | Conditional branch instructions that determine execution flow. |
| U-Type | Upper immediate instructions, used for loading large constants. |
| J-Type | Jump instructions for function calls and unconditional jumps. |
| C-Type | Compressed 16-bit instructions that optimize code size. |

## Instruction Format Breakdown

| Type | Format Representation |
|------|------------------------|
| R-Type | funct7 (7) | rs2 (5) | rs1 (5) | funct3 (3) | rd (5) | opcode (7) |
| I-Type | imm[11:0] (12) | rs1 (5) | funct3 (3) | rd (5) | opcode (7) |
| S-Type | imm[11:5] (7) | rs2 (5) | rs1 (5) | funct3 (3) | imm[4:0] (5) | opcode (7) |
| B-Type | imm[12] (1) | imm[10:5] (6) | rs2 (5) | rs1 (5) | funct3 (3) | imm[4:1] (4) | imm[11] (1) | opcode (7) |
| U-Type | imm[31:12] (20) | rd (5) | opcode (7) |
| J-Type | imm[20] (1) | imm[10:1] (10) | imm[11] (1) | imm[19:12] (8) | rd (5) | opcode (7) |
| C-Type | Varies based on specific compressed instruction encoding |

### Explanation of Fields:
- **opcode (7 bits):** Identifies the operation to be performed.
- **rd (5 bits):** Destination register.
- **funct3 (3 bits):** Specifies the operation variant.
- **rs1, rs2 (5 bits each):** Source registers.
- **funct7 (7 bits):** Further differentiates operations (mainly in R-Type).
- **imm (various sizes):** Immediate values for computation or memory addresses.

## Pseudo Instructions

Pseudo instructions are assembly-level mnemonics that simplify programming by providing more readable representations of common instruction sequences. The assembler translates these into standard RISC-V instructions.

| Pseudo Instruction | Equivalent Actual Instruction |
|--------------------|-----------------------------|
| `li rd, imm` | `addi rd, x0, imm` |
| `mv rd, rs` | `addi rd, rs, 0` |
| `not rd, rs` | `xori rd, rs, -1` |
| `neg rd, rs` | `sub rd, x0, rs` |
| `bgt rs1, rs2, label` | `blt rs2, rs1, label` |
| `ble rs1, rs2, label` | `bge rs2, rs1, label` |
| `call func` | `jal x1, func` |
| `ret` | `jalr x0, 0(x1)` |

Pseudo instructions make assembly programming easier, but they are internally converted into one or more actual RISC-V instructions by the assembler.

