Register Transfer:
P: R2<--R1

Bus and Memory Transfers:
- Using Multiplexers
- Using Tri-state Buffers
Memory Transfer:
- Read: DR <-- M[AR]
- Write: M[AR] <-- DR
Types of Micro-operations:
- Register Transfer Micro-operations
	- Transfer
- Arithmetic Micro-operations
	- Add (with and without carry)
	- Sub (with and without borrow)
	- Increment
	- Decrement
	- Instructions
		- Negate (2's complement)
- Logical Micro-operations
	- 0
	- xy
	- xy'
	- x
	- x'y
	- y
	- x xor y
	- x+y
	- (x+y)'
	- (x xor y)'
	- y'
	- x+y'
	- x'
	- x'+y
	- (xy)'
	- 1
	- Instructions
		- Clear
		- Clear carry
		- Complement
		- Complement carry
		- Enable Interrupt
		- Disable Interrupt
	- Application
		- Selective set
		- Selective complement
		- Selective clear
		- mask
		- clear
- Shift Micro-operations
	- shl
	- shr
	- cil
	- cir
	- ashl
	- ashr
	- Instructions
		- Rotate left with carry
		- Rotate right with carry
ALU

Instruction Codes
- Mode [optional]
- Operation code (Opcode)
- Address (operand)

Registers
- DR 16 Data Register
- AR 12 Address Register
- AC 16 Accumulator
- IR 16 Instruction Register
- PC 12 Program counter
- TR 16 Temporary Register
- INPR 8 Input Register
- OUTR 8 Output Register

Register-Reference Instructions:
- Clear SC
- Clear AC
- Clear E
- Complement AC
- Complement E
- Circulate right Circulate left
- Increment AC
- Skip if positive Skip if negative
- Skip if AC zero
- Skip if E zero Halt computer

Memory-Reference Instructions:
- AND
- ADD
- LDA Load AC
- STA Save AC to memory
- BUN AR to PC
- BSA branching
- ISZ Increment and Skip if Zero


Addressing Modes
- Implied
- Immediate
- Register
- Register Indirect
- Direct Address
- Indirect Address
- Auto Increment or Decrement
- Relative
- Indexed
- Base Register addressing




Data types
- Numbers
- Letters
- Others

Hex 0 to F -> 0000 to 1111
Dec 0 to 9 -> 0000 to 1001
Oct 0 to 7 -> 000 to 111
ASCII 
- A to Z -> 100 0001 to 101 1010
- 1 to 9 -> 011 0000 to 011 1001
- others 010 0000 to 011 1101

Complement
- (r-1)'s complement (r^n-1)-N
- r's complement  (r^n-1)-N + 1

Fixed point representation
F = m x r^e
F = mantissa x radix to the power exponent

Multiplication
if Q0 = 0 Shift right
if Q0 = 1 Add M, shift right

Division
if E = 0 Add B
if E = 1 Sub B, Shl EAQ