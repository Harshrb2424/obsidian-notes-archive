
- Shift microoperations are used for serial data transfer.
- Contents of a register can be shifted left or right.
- Three types of shifts: logical, circular, and arithmetic.
- Symbolic notation for shift microoperations in Table 4-7.
![[Pasted image 20231110204432.png]]
## Logical Shift

- Transfers 0 through the serial input.
- Symbols: `shl` for shift-left and `shr` for shift-right.
- 1-bit shift to the left (shl) and right (shr) shown in Table 4-7.
- During logical shift, the bit transferred through the serial input is assumed to be 0.

## Circular Shift

- Circulates bits of the register without loss of information.
- Symbols: `cil` for circular shift-left and `cir` for circular shift-right.
- Achieved by connecting serial output to serial input.

## Arithmetic Shift

- Shifts a signed binary number left or right.
- Shift-left multiplies a signed binary number by 2.
- Shift-right divides the number by 2.
- Must leave the sign bit unchanged to maintain the number's sign.
![[Pasted image 20231110204419.png]]
## Hardware Implementation

- Combinational circuit shifter constructed with multiplexers (Fig. 4-12).
- Shifts right when selection input (S) is 0 and left when S = 1.
- Shifter with n data inputs/outputs requires n multiplexers.
- Two serial inputs controlled by another multiplexer to provide three types of shifts.
![[Pasted image 20231110204410.png]]
## Arithmetic Logic Shift Unit
![[Pasted image 20231110204341.png]]
- Computer systems use an Arithmetic Logic Unit (ALU) for microoperations.
- ALU is a combinational circuit connected to storage registers.
- Shift microoperations can be part of the ALU.
- One stage of an arithmetic logic shift unit shown in Fig. 4-13.
- Selection variables S1, S0, S3, S2, and Cin determine the operation.
- Table 4-8 lists 14 operations of the ALU (8 arithmetic, 4 logic, 2 shift).
![[Pasted image 20231110204326.png]]