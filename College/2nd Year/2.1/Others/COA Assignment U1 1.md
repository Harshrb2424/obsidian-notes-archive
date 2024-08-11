1. **a) Explain the logical Micro operations.**
   **b) Discuss about Arithmetic Logic Shift Unit.**
# 1. a) Logic Micro-operations

- Logic micro-operations specify binary operations for bit strings in registers.
- Each bit in the register is treated as a binary variable.
- Example: Exclusive-OR micro-operation between registers R1 and R2 when the control variable P = 1.
![[Pasted image 20231110204147.png]]
## List of Logic Microoperations

- 16 different logic operations for two binary variables.
- Derived from truth tables with two binary variables (see Table 4-5).
- Expressions in Table 4-6 show Boolean functions for variables x and y.
- Logic micro-operations derived by replacing x with content of register A and y with content of register B.
![[Pasted image 20231110204200.png]]
# 1. b) Arithmetic Logic Shift Unit
![[Pasted image 20231110204341.png]]
- Computer systems use an Arithmetic Logic Unit (ALU) for microoperations.
- ALU is a combinational circuit connected to storage registers.
- Shift microoperations can be part of the ALU.
- One stage of an arithmetic logic shift unit shown in Fig. 4-13.
- Selection variables S1, S0, S3, S2, and Cin determine the operation.
- Table 4-8 lists 14 operations of the ALU (8 arithmetic, 4 logic, 2 shift).
![[Pasted image 20231110204326.png]]
2. **a) Explain the hardware implementation of Logic Micro operations.**
   **b) Draw the instruction code Format.**
# 2. a) Hardware Implementation

- Logic microoperations hardware implementation uses logic gates for each bit or pair of bits in registers.
- Most computers use four basic logic microoperations: AND, OR, XOR (exclusive-OR), and complement.
- Circuit example for generating basic logic microoperations using gates and a multiplexer.
![[Pasted image 20231110204211.png]]
## Some Applications

- Logic micro-operations useful for manipulating individual bits or portions of a word in a register.
- Examples of applications:
  - Selective set
  - Selective complement
  - Selective clear
  - Mask
  - Insert
  - Clear

### Selective Set

- Sets to 1 the bits in register A where there are corresponding 1's in register B.
- OR microoperation used for selective setting.

### Selective Complement

- Complements bits in A where there are corresponding 1's in B.
- Exclusive-OR microoperation used for selective complementing.

### Selective Clear

- Clears to 0 the bits in A where there are corresponding 1's in B.
- Corresponding logic microoperation is AND.

### Mask

- Similar to selective clear, but clears bits in A only where there are corresponding 0's in B.
- Mask operation is an AND microoperation.

### Insert

- Inserts a new value into a group of bits by masking unwanted bits and ORing with the required value.
- Example provided for inserting a value into a register.

### Clear

- Compares words in A and B, produces all 0's result if the two numbers are equal.
- Achieved by an exclusive-OR microoperation.

# 2. b) Instruction Codes
![[Basic Computer Organization and Design#Instruction Codes]]
3. **a) Explain the computer registers.**
   **b) Explain the timing and control signal with help of timing diagram**
# 3. a)
![[Basic Computer Organization and Design#Computer Registers]]
# 3. b)
![[Basic Computer Organization and Design#Timing and Control]]