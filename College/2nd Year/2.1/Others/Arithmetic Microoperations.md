# Arithmetic Micro-operations

- Basic arithmetic micro-operations include:
  - Addition
  - Subtraction
  - Increment
  - Decrement
  - Shift
![[Pasted image 20231110203946.png]]
- The arithmetic micro-operation `R3 ← R1 + R2` specifies adding the contents of R1 to R2 and storing the sum in R3.
- Hardware requirements for addition: 3 registers and a digital component for addition.
- Subtraction is often implemented through complementation and addition. The subtract operation is defined as `R3 ← R1 + R2 + 1`.
- 1's complement of R2 is used instead of the minus operator. Adding 1 to 1's complement produces 2's complement.

## Binary Adder
- Full Adder: A digital circuit for the arithmetic sum of 2 bits and the previous carry.
- Binary Adder: Generates the arithmetic sum of 2 binary numbers; multiple full-adders are used.
- Example: Interconnections of four full-adders to provide a 4-bit binary adder.

## Binary Adder – Subtractor
- Addition and subtraction combined using an exclusive-OR gate with each full-adder.
- 4-bit adder-subtractor circuit with a mode input (M) to control operation (0 for add, 1 for subtract).
![[Pasted image 20231110203959.png]]
## Binary Incrementer
- Increment micro-operation adds one to a number in a register.
- Implemented using half-adders connected in cascade.
- Example: Diagram of a 4-bit combinational circuit incrementer.
- Output carry (C4) is 1 only after incrementing binary 1111.
![[Pasted image 20231110204014.png]]
## Arithmetic Circuit
- Basic component: Parallel adder.
- Diagram of a 4-bit arithmetic circuit with multiplexers for different operations.
- Inputs A and B, output D, and control inputs S1 and S0 for various arithmetic micro-operations.
![[Pasted image 20231110204050.png]]
![[Pasted image 20231110204103.png]]
### Arithmetic Micro-operations Table
- Addition (S1S0 = 00): D = A + B or D = A + B + 1 (with carry).
- Subtraction (S1S0 = 01): D = A - B or D = A - B - 1 (with borrow).
- Increment (S1S0 = 10): D = A or D = A + 1.
- Decrement (S1S0 = 11): D = A - 1.
