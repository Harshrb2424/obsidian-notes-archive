# Digital Systems and Register Transfer Language

## Digital Systems Overview
- A digital system is an interconnection of digital hardware modules.
- Modules include registers, decoders, arithmetic elements, and control logic.
- These modules are interconnected with common data and control paths to form a digital computer system.

## Microoperations and Registers
- Digital modules are defined by the registers they contain and the operations performed on the data stored in them.
- Microoperations are elementary operations on information stored in registers.
- Examples of microoperations include shift, count, clear, and load.

## Register Transfer Language (RTL)
- RTL is a symbolic notation used to describe micro-operation transfer among registers.
- It provides an organized and concise way to represent micro-operation sequences and control functions.

## Registers
![[Pasted image 20231110203332.png]]
- Computer registers are designated by uppercase letters, denoting their function (e.g., MAR, PC, IR, R1).
- Individual flip-flops in an n-bit register are numbered from 0 through n-1.
- Registers can be represented in block diagram form, with bits marked and labeled as low (L) or high (H) bytes.

## Register Transfer

![[Pasted image 20231110203350.png]]

- Register transfer is symbolized with an arrow (R2 ← R1), denoting the transfer of content from one register to another.
- Control conditions, represented by a Boolean variable (e.g., P), can determine when a transfer occurs.
- **Letters (and Numerals):**
    
    - Denotes a register.
    - Examples: MAR, R2.
- **Parentheses ( ):**
    
    - Denotes a part of a register.
    - Examples: R2(0-7), R2(L).
- **Arrow <--:**
    
    - Denotes transfer of information from one register to another.
    - Example: R2 <-- R1.
- **Comma ,:**
    
    - Separates two microoperations.
    - Examples: R2 <-- R1, R1 <-- R2.

## Common Bus System with Multiplexers

In a computer architecture, a common bus system with multiplexers is an efficient way to transfer information between registers. Here's a breakdown of the key elements described in your passage:

1. **Common Bus System:**
   - A set of common lines, one for each bit of a register.
   - Allows for the transfer of information between different registers.

2. **Multiplexers:**
   - Components used to select the source register whose binary information is placed on the bus.
   - For example, a 4 x 1 multiplexer has four data inputs (0 through 3) and two selection inputs (S1 and S0).

3. **Construction of the Bus System:**
   - Each bit in the same significant position of each register is connected to the data inputs of a multiplexer.
   - Multiplexers are used to choose the bits from a selected register and transfer them to the common bus.

4. **Selection Inputs (S1 and S0):**
   - Two selection lines that determine which register is selected and transferred to the bus.
   - Binary values on S1 and S0 determine the specific register to be connected to the bus.

5. **Operation:**
   - When S1S0 = 00, the 0 data inputs of all multiplexers are selected, and the content of the corresponding register is transferred to the bus.
   - The process is repeated for different binary values of S1S0, selecting different registers.

6. **Table 4-2:**
   - Shows the register selected by the bus for each possible binary value of the selection lines.
![[Pasted image 20231110203446.png]]
7. **General Characteristics:**
   - A bus system typically involves multiplexing "k" registers.
   - Each register has "n" bits, contributing to an "n-line bus."
   - The number of multiplexers required is "n," and the size of each multiplexer is "k x 1."

8. **Register Transfer Symbolization:**
   - The bus inclusion in a statement is symbolized as follows:
     - `BUS← C`: The content of register C is placed on the bus.
     - `R1← BUS`: The content of the bus is loaded into register R1 by activating its load control input.
![[Pasted image 20231110203456.png]]
## Three-State Bus Buffers
- A bus system can use three-state gates for efficient information transfer between registers.
- Three-state buffers have three states: logic 1, logic 0, and high-impedance (open circuit).
- Bus systems can be constructed using multiplexers or three-state buffers.
![[Pasted image 20231110203623.png]]![[Pasted image 20231110203632.png]]
## Memory Transfer
- Memory transfer involves reading and writing operations.
- Memory word (M) is selected by an address during the transfer.
- Read operation: `DR <- M[AR]` transfers information from the memory word M to the data register.
- Write operation: `M[AR] <- R1` transfers information from register R1 to the memory word M.

## Types of Micro-operations
1. **Register Transfer Micro-operations:** Transfer binary information between registers.
2. **Arithmetic Micro-operations:** Perform arithmetic operations on numeric data stored in registers.
3. **Logical Micro-operations:** Perform bit manipulation operations on data stored in registers.
4. **Shift Micro-operations:** Perform shift operations on data stored in registers.

Note: Register Transfer Micro-operations do not change the information content during the transfer, while the other three types may alter the information content.