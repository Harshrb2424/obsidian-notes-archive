# Addressing Modes

- The way operands are chosen during program execution depends on the addressing mode of the instruction.

- Computers use addressing mode techniques to provide programming versatility and to reduce the number of bits in the addressing field of the instruction.

- Most addressing modes modify the address field of the instruction; two modes that need no address field at all are implied and immediate modes.
![[Pasted image 20231122223046.png]]
## Implied Mode:

- In this mode, operands are specified implicitly in the definition of the instruction.
  
- For example, the instruction "complement accumulator" is an implied-mode instruction because the operand in the accumulator register is implied in the definition of the instruction.

- All register reference instructions that use an accumulator are implied mode instructions.

- Zero address in a stack organization computer is implied mode instructions.

## Immediate Mode:

- In this mode, the operand is specified in the instruction itself.

- Immediate-mode instructions are useful for initializing registers to a constant value.

- The address field of an instruction may specify either a memory word or a processor register.

- When the address specifies a processor register, the instruction is said to be in the register mode.

## Register Mode:

- In this mode, the operands are in registers that reside within the CPU.

- The particular register is selected from a register field in the instruction.

## Register Indirect Mode:

- In this mode, the instruction specifies a register in the CPU whose contents give the address of the operand in memory.

- The selected register contains the address of the operand rather than the operand itself.

- The advantage is that the address field of the instruction uses fewer bits to select a register than would have been required to specify a memory address directly.

## Auto-increment or Auto-Decrement Mode:

- Similar to the register indirect mode, but the register is incremented or decremented after (or before) its value is used to access memory.

- The address field of an instruction is used by the control unit in the CPU to obtain the operand from memory.

- Sometimes the value given in the address field is the address of the operand, but sometimes it is just an address from which the address of the operand is calculated.

## Direct and Indirect Address Modes:

### Direct Address Mode:

- In this mode, the effective address is equal to the address part of the instruction.

- The operand resides in memory, and its address is given directly by the address field of the instruction.

- In a branch-type instruction, the address field specifies the actual branch address.

### Indirect Address Mode:

- In this mode, the address field of the instruction gives the address where the effective address is stored in memory.

- Control fetches the instruction from memory and uses its address part to access memory again to read the effective address.

- A few addressing modes require that the address field of the instruction be added to the content of a specific register in the CPU.

- The effective address in these modes is obtained from the following computation:
  `Effective address = address part of instruction + content of CPU register`

- The CPU register used in the computation may be the program counter, an index register, or a base register.

## Special Addressing Modes:

### Relative Address Mode:

- In this mode, the content of the program counter is added to the address part of the instruction to obtain the effective address.

### Indexed Addressing Mode:

- In this mode, the content of an index register is added to the address part of the instruction to obtain the effective address.

- An index register is a special CPU register that contains an index value.

### Base Register Addressing Mode:

- In this mode, the content of a base register is added to the address part of the instruction to obtain the effective address.

- This is similar to the indexed addressing mode except that the register is now called a base register instead of an index register.
