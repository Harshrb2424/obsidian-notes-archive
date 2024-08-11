# Instruction Codes

- The organization of the computer is defined by its internal registers, timing and control structure, and the set of instructions.
- Instructions are stored in memory and executed based on their opcode and operand.

## Instruction Code Format
![[Pasted image 20231112121853.png]]
- Instruction codes are divided into two parts: Opcode and Address (Operand).
- **Operation Code (Opcode):**
  - Specifies the operation (add, subtract, etc.).
  - Number of bits required depends on the number of operations.
- **Address (Operand):**
  - Specifies the location of operands (registers or memory words).

## Stored Program Organization

- Stored program organization allows storing instructions in memory and executing them sequentially.
- Example instruction format: 16-bit word with 3-bit opcode and 12-bit address.
![[Pasted image 20231112121909.png]]
## Addressing of Operand

- Immediate Operand: Operand is part of the instruction.
- Direct Address: Operand is specified by the address part of the instruction.
- Indirect Address: Address of the operand is found in another memory location.
- Addressing modes are determined by a mode bit (0 for direct, 1 for indirect).
![[Pasted image 20231112121922.png]]
# Computer Registers

- Registers play a crucial role in instruction sequencing and data manipulation.
- Common registers include Accumulator (AC), Instruction Register (IR), Program Counter (PC), etc.
![[Pasted image 20231112121953.png]]
## Common Bus System

- A common bus system efficiently transfers information between registers and memory.
- Selection variables determine which register's output is connected to the bus.
- Load (LD), Increment (INR), and Clear (CLR) control inputs are used for register operations.
![[Pasted image 20231112122009.png]]
## Example Registers

- Example registers include Data Register (DR), Temporary Register (TR), Memory Address Register (AR), etc.
- Input and output registers (INPR and OUTR) communicate with external devices.

## Adder and Logic Circuit

- The Adder and Logic Circuit perform arithmetic operations and logical functions.
- Multiple inputs, including content from registers, enable versatile operations.
- Operations can be executed in parallel during the same clock cycle.

# Computer Instructions

- The basic computer has three instruction code formats, each with 16 bits.
- The operation code (opcode) part of the instruction contains three bits, and the remaining 13 bits depend on the opcode.
  ![[Pasted image 20231112122115.png]]
## Memory-Reference Instruction

- Uses 12 bits to specify an address and one bit (I) for addressing mode (0 for direct, 1 for indirect).
![[Pasted image 20231112122118.png]]
## Register-Reference Instruction

- Identified by opcode 1.11 with a 0 in the leftmost bit (bit 15).
- Specifies an operation on the AC register; does not require an operand from memory.
- The other 12 bits are used to specify the operation to be executed.

## Input-Output Instruction

- Recognized by opcode 111 with a 1 in the leftmost bit.
- Does not require a memory reference; the remaining 12 bits specify the input-output operation.

## Instruction Set

- Instructions are listed in Table 5-2 with symbolic designations and hexadecimal codes.

## Instruction Set Completeness

- A complete instruction set should include categories like arithmetic, logical, shift, data movement, program control, and input-output instructions.
- Example instructions include ADD, CMA, INC for arithmetic, and LDA, STA for data movement.
- Branch instructions (BUN, BSA, ISZ) and skip instructions provide program control.
- Input (INP) and output (OUT) instructions facilitate data transfer between the computer and external devices.

# Timing and Control

- The timing for all registers in the basic computer is controlled by a master clock generator.
- Clock pulses are applied to all flip-flops and registers in the system when enabled by a control signal.
- Control signals, generated in the control unit, control multiplexers, processor registers, and microoperations.
![[Pasted image 20231112122234.png]]
## Control Organizations

### Hardwired Control

- Implemented with gates, flip-flops, decoders, and other digital circuits.
- Control information is stored in the control memory, programmed for the required sequence of microoperations.
- Advantages include optimization for faster operation.
- Changes in design require modifications in wiring among components.

### Microprogrammed Control

- Control logic is stored in control memory.
- The control memory is programmed to initiate the required sequence of microoperations.
- Offers flexibility for modifications by updating the microprogram.

## Hardwired Control Unit

- Block diagram includes two decoders, a sequence counter, and control logic gates.
- Instruction from memory is placed in the instruction register (IR), divided into I bit, operation code, and bits 0-11.
- Operation code (bits 12-14) is decoded with a 3x8 decoder, producing outputs D0 through D7.
- Bit 15 of the instruction is transferred to a flip-flop (I).
- Bits 0-11 are applied to control logic gates.
- Sequence counter (SC) can count in binary from 0 through 15.
- Outputs of SC are decoded into 16 timing signals (T0-T15).
- SC can be incremented or cleared synchronously.
- Timing diagram shows the time relationship of control signals.

### Timing Diagram

- SC responds to the positive transition of the clock.
- Initially, the CLR input of SC is active.
- SC is incremented with every positive clock transition unless CLR input is active.
- The timing diagram illustrates the sequence of timing signals and the clearing of SC based on control signals.
![[Pasted image 20231112122228.png]]
# Instruction Cycle

- A program in the computer's memory consists of a sequence of instructions.
- Each instruction cycle is subdivided into phases: fetch, decode, read effective address (if indirect), and execute.
- Phases are repeated for each instruction in the program.

## Phases of the Instruction Cycle

1. **Fetch an instruction from memory:**
   - Program counter (PC) loaded with the address of the first instruction.
   - Sequence counter (SC) cleared to 0.
   - Microoperations:
     - Transfer content of PC to Address Register (AR).
     - Enable read input of memory.
     - Place memory content onto the bus.
     - Transfer bus content to Instruction Register (IR).
     - Increment PC.

2. **Decode the instruction:**
   - Control unit determines the instruction type.
   - Decoder output D7 checked; if 1, register-reference or input-output type.
   - If D7 = 0:
     - Check I bit (flip-flop I).
     - If I = 1, memory-reference instruction with an indirect address; read effective address.
     - If I = 0, memory-reference instruction with a direct address.
![[Pasted image 20231112122347.png]]
3. **Read the effective address (if the instruction has an indirect address):**
   - Additional phase for memory-reference instructions with an indirect address.
   - If D7 = 0 and I = 1, read the effective address from memory.

4. **Execute the instruction:**
   - Perform the actual operation specified by the instruction.
   - Control transitions back to the fetch phase for the next instruction.

## Determine the Type of Instruction

- Control unit determines the instruction type based on the decoding phase.
- Decoder output D7 and flip-flop I used to categorize instructions into memory-reference, register-reference, or input-output.
![[Pasted image 20231112122352.png]]
## Register-Reference Instructions

- Recognized when D7 = 1 and I = 0.
- Use bits 0-11 of the instruction code to specify 12 instructions.
- Control functions and microoperations listed in Table 5-3.
- Execution completed at time T3; SC cleared to 0, control goes back to fetch the next instruction.

## Example Instruction: CLA (Clear AC)

- Hexadecimal code: 7800 (binary: 0111 1000 0000 0000).
- Control function: D7I’T3 B11 = rB11.
- Execution completed at time T3; SC cleared to 0, control goes back to fetch the next instruction.

- The first seven register-reference instructions perform clear, complement, circular shift, and increment microoperations on the AC or E registers.
- The next four instructions cause a skip of the next instruction in sequence when a stated condition is satisfied.
![[Pasted image 20231112122357.png]]
## HLT Instruction

- The HLT instruction clears a start-stop flip-flop S and stops the sequence counter from counting.

# Memory-Reference Instructions

- Table 5-4 lists seven memory-reference instructions with decoded outputs Di from the operation decoder.
- Effective address is in the address register AR.
- Execution of memory-reference instructions starts with timing signal T4.
![[Pasted image 20231112122535.png]]
## AND to AC

- Performs the AND logic operation on AC and the memory word specified by the effective address.
- Result transferred to AC.
- Microoperations:
  - Transfer memory word to Data Register (DR).
  - Perform AND operation between AC and DR.
  - Transfer result to AC.

## ADD to AC

- Adds the content of the memory word specified by the effective address to the value of AC.
- Sum transferred to AC; output carry Cout transferred to the E (extended accumulator) flip-flop.
- Microoperations:
  - Transfer memory word to DR.
  - Add DR to AC.

## LDA: Load to AC

- Transfers the memory word specified by the effective address to AC.
- Microoperations:
  - Transfer memory word to DR.
  - Transfer DR to AC.

## STA: Store AC

- Stores the content of AC into the memory word specified by the effective address.
- Microoperations:
  - Transfer AC to memory word.

## BUN: Branch Unconditionally

- Transfers the program to the instruction specified by the effective address.
- Microoperations:
  - Transfer effective address to PC.

## BSA: Branch and Save Return Address

- Useful for branching to a subroutine.
- Stores the address of the next instruction in sequence (available in PC) into a memory location specified by the effective address.
- Effective address plus one transferred to PC.
- Microoperations:
  - Store return address in memory.
  - Transfer effective address plus one to PC.
![[Pasted image 20231112122530.png]]
## ISZ: Increment and Skip if Zero

- Increments the word specified by the effective address.
- If incremented value is zero, PC is incremented by 1 to skip the next instruction.
- Microoperations:
  - Transfer memory word to DR.
  - Increment DR.
  - Store DR back into memory.
  - Skip next instruction if DR is zero.

## Control Flowchart

- A flowchart showing all microoperations for the execution of the seven memory-reference instructions.
![[Pasted image 20231112122516.png]]


# Input-Output and Interrupt

## Input-Output Configuration

- The terminal unit has a keyboard and printer, communicating serially with eight bits of an alphanumeric code.
- Input register (INPR) receives serial information from the keyboard.
- Output register (OUTR) stores serial information for the printer.
- Communication interface between registers and the Accumulator (AC).
- Input flag (FGI) and output flag (FGO) control information flow.

## Input-Output Instructions

- Recognized by control when D7 = 1 and I = 1.
- Executed with the clock transition associated with timing signal T3.
- Control functions and microoperations listed in Table 5-5.
- Each control function needs a Boolean relation D7IT3 (designated by symbol p).
- Control functions distinguished by bits in IR (6-11).
- Sequence counter SC cleared to 0 when p = D7IT3 = 1.

### Input-Output Instructions List:
![[Pasted image 20231112122714.png]]
1. **Read Input (RDI):**
   - Reads data from the input device.
   - Sets FGI to 0 after reading.

2. **Write Output (WO):**
   - Writes data to the output device.
   - Sets FGO to 0 after writing.

3. **Check Input Flag (CIF):**
   - Checks if FGI is set (new information available).
   - Result (1 or 0) transferred to AC.

4. **Check Output Flag (COF):**
   - Checks if FGO is set (output device ready).
   - Result (1 or 0) transferred to AC.

5. **Clear Input Flag (CIF):**
   - Clears FGI to 0.

6. **Clear Output Flag (COF):**
   - Clears FGO to 0.

7. **Interrupt Enable (ION):**
   - Sets IEN flip-flop (enables interrupts).

8. **Interrupt Disable (IOF):**
   - Clears IEN flip-flop (disables interrupts).
![[Pasted image 20231112122705.png]]
## Program Interrupt

- Interrupts used for efficient input and output communication.
- Interrupts occur when external device signals readiness.
- Interrupt enable flip-flop (IEN) set and cleared by instructions.
- Interrupt cycle initiated when IEN = 1 and flag is set.
- Interrupt cycle is a hardware implementation of a branch and save return address operation.
- Interrupt cycle flowchart explained in Fig. 5-13.
![[Pasted image 20231112122659.png]]
### Interrupt Cycle Steps:

1. **Check IEN:**
   - If IEN = 0, continue with the next instruction cycle.
   - If IEN = 1, proceed to the next step.

2. **Check Flags:**
   - If both flags are 0, continue with the next instruction cycle.
   - If either flag is 1, set interrupt flip-flop R to 1.

3. **Interrupt Cycle:**
   - During interrupt cycle, store return address in a specific location.
   - Transfer control to an interrupt service routine.
   - After service routine execution, set IEN to 1 and return to the interrupted program.
![[Pasted image 20231112122656.png]]
## Example:

- Example interrupt cycle and program flow shown in Fig. 5-14.
