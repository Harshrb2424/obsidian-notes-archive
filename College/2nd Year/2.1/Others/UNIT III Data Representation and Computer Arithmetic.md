- Data Representation

	- [[Data Types 1]]
	- Complements
	- Fixed Point Representation
	- Floating Point Representation

- Computer Arithmetic

	- Addition and Subtraction
	- Multiplication Algorithms
	- Division Algorithms
	- Floating–Point Arithmetic Operations
	- Decimal Arithmetic Unit
	- Decimal Arithmetic Operations

# Data Representation

## Data Types
## Complements
## Fixed Point Representation
## Floating Point Representation

# Computer Arithmetic
## Digital **Computer Arithmetic** Operations
Data is manipulated by using arithmetic instructions in digital computers. The goal is to produce results necessary for solving computational problems. The four basic arithmetic operations are:

- Addition
- Subtraction
- Multiplication
- Division

Other operations can be derived by combining these basic operations.

### Arithmetic Processing Unit

To execute arithmetic operations, there is a separate section called the arithmetic processing unit in the central processing unit. These operations are typically performed on binary or decimal data. Fixed-point numbers are used to represent integers or fractions, which can be signed or unsigned.

Fixed-point addition is the simplest arithmetic operation.

### Algorithm for Problem Solving

To solve a problem, a sequence of well-defined steps, collectively called an algorithm, is used. Algorithms are provided to solve various problems.

### Computational Problem Solving

Arithmetic instructions play a crucial role in processing data in a digital computer. These instructions are used to perform arithmetic calculations. The four basic operations—addition, subtraction, multiplication, and division—form the foundation for solving scientific problems through numerical analysis methods.

### Arithmetic Processor in a Processor

A processor contains an arithmetic processor as a sub-part, responsible for executing arithmetic operations. The data type, assumed to reside in processor registers during execution, includes negative numbers represented in signed magnitude or signed complement representation.

### Representation of Negative Fixed-Point Binary Numbers

There are three ways of representing negative fixed-point binary numbers:

1. Signed Magnitude
2. Signed 1’s Complement
3. Signed 2’s Complement

Most computers use the signed magnitude representation for the mantissa.

## Addition and Subtraction

In the context of signed-magnitude data, the magnitude of two numbers (A and B) is designated. For both addition and subtraction of signed numbers, eight different conditions need consideration based on the signs and the operation performed. These conditions are outlined in the first column of Table 4.1. The table illustrates the actual operations to be performed along with the magnitude of the numbers. The last column is essential to represent negative zero, ensuring that when two equal numbers are subtracted, the result is +0, not -0.

### SIGNED MAGNITUDE ADDITION AND SUBTRACTION Algorithm

### Addition:
1. Load A and B registers.
2. Complement B.
3. Perform parallel addition of A and B.
4. Check for overflow, and store the result in the output register.

### Subtraction:
1. Load A and B registers.
2. Perform parallel addition of A and 2's complement of B.
3. Check for overflow and clear the add-overflow flip-flop (AVF).
4. Determine the sign of the result based on the sign of A.
5. If A < B, take the 2's complement of A.
6. The final result is in register A, and AVF indicates overflow.

### SIGNED 2’S COMPLEMENT ADDITION AND SUBTRACTION

### Algorithm:
1. Compare signs A and B using an exclusive-OR gate.
2. If output is 0, signs are identical; if 1, signs are different.
3. For addition, add magnitudes; for subtraction, add magnitudes when signs are different.
4. Check for overflow and update AVF.
5. For subtraction, obtain 2's complement of A when A < B.
6. Ensure correct sign for the result.

### Hardware:
- Registers A and B
- Sign flip-flops As and Bs
- Add-overflow flip-flop AVF
- Overflow checking with flip-flop E
- Output carry transferred to flip-flop E for magnitude comparison
- Result in register A with sign indication in As

### Multiplication Algorithms
In the multiplication algorithm, the multiplicand is initially in register B, and the multiplier is in register Q. Their corresponding signs are in Bs and Qs, respectively. The process follows these steps:

1. **Initialization:**
   - Clear registers A and E.
   - Set the sequence counter SC to the number of bits in the multiplier.
   - Compare the signs of A and Q and set the corresponding sign for the product.

2. **Partial Product Calculation:**
   - Test the low-order bit of the multiplier (Qn).
   - If it is 1, add the multiplicand (B) to the present partial product (A); otherwise, proceed.
   - Shift the register EAQ once to the right to form the new partial product.
   - Decrement the sequence counter by 1 and check its new value.
   - Repeat the process until SC becomes zero.

### Booth's Algorithm

Booth's algorithm provides a procedure for multiplying binary integers in signed-2’s complement representation. It takes advantage of strings of 0’s and 1’s in the multiplier:

- Strings of 0’s require only shifting, and strings of 1’s can be treated as \(2^{k+1} - 2^m\).
- Booth's algorithm involves examining the multiplier bits and shifting the partial product.

### Rules for Shifting:

1. Subtract the multiplicand from the partial product upon encountering the first least significant 1 in a string of 1’s in the multiplier.
2. Add the multiplicand to the partial product upon encountering the first 0 in a string of 0’s in the multiplier.
3. The partial product remains unchanged when the multiplier bit is identical to the previous multiplier bit.

### Operation:

- The two bits of the multiplier in Qn and Qn+1 are inspected.
- If the two bits are equal to 10, subtract the multiplicand from the partial product.
- If the two bits are equal to 01, add the multiplicand to the partial product.
- When the two bits are equal, the partial product does not change.

Booth's algorithm works for positive or negative multipliers in 2’s complement representation. Negative multipliers end with a string of 1’s, and the last operation will be a subtraction of the appropriate weight.
## Division Algorithms

The division of two fixed-point binary numbers in signed-magnitude representation is carried out through successive compare, shift, and subtract operations. Binary division is simpler than decimal division since quotient digits are limited to 0 or 1, eliminating the need to estimate how many times the dividend or partial remainder fits into the divisor.

The division process is outlined in the provided figure. The divisor is compared with the five most significant bits of the dividend, and the process is repeated until the sequence counter reaches zero. The quotient and remainder are obtained through successive iterations of partial remainders and comparisons.

### Hardware Implementation for Signed-Magnitude Data

In the hardware implementation for signed-magnitude data, a modification is introduced. Instead of shifting the divisor to the right, two dividends or partial remainders are shifted to the left, simplifying the hardware requirements. Subtraction is achieved by adding the multiplicand to the 2's complement of the multiplier. The end carry provides information about the relative magnitudes.

### Example of Binary Division with Digital Hardware

The process is illustrated through a detailed example, where the divisor is stored in the B register, and the double-length dividend is stored in registers A and Q. The dividend is shifted to the left, and the divisor is subtracted by adding its 2's complement value.

## Floating–Point Arithmetic Operations
In many high-level programming languages, floating-point numbers are specified using a real declaration statement. Floating-point arithmetic operations are typically built into the internal hardware of computers. There are two parts to a floating-point number: a mantissa (m) and an exponent (e). The number is represented as \(m \times r^e\), where \(r\) is the radix.

### Basic Considerations

A floating-point number consists of a mantissa and an exponent, representing a number generated by multiplying the mantissa by a radix raised to the power of the exponent. The mantissa can be a fraction or an integer. Floating-point numbers are said to be normalized if the most significant digit of the mantissa is nonzero.

Floating-point representation increases the range of numbers for a given register. Arithmetic operations with floating-point numbers are more complex than with fixed-point numbers, requiring alignment of the radix point before addition or subtraction.

### Register Configuration

The register configuration for floating-point operations includes registers BR, AC, and QR. Each register is subdivided into two parts - a mantissa part and an exponent part. The mantissa operations are similar to fixed-point numbers, while the exponent operations involve comparison, addition, subtraction, and normalization.

This concludes the summary of the provided information in Markdown format. Adjustments can be made as needed.

Assuming that each floating-point number has a mantissa in signed-magnitude representation and a biased exponent, the AC (Accumulator) has a mantissa whose sign is in As, and a magnitude that is in A. Similarly, the register BR (Buffer Register) is subdivided into Bs, B, and b, and QR (Quotient Register) into Qs, Q, and q. A parallel-adder adds the two mantissas and loads the sum into A, with the carry into E (Exponent).

In the same way, a separate parallel adder can be used for the exponents. The exponents do not have a distinct sign bit because they are biased but are represented as a biased positive quantity. It is assumed that the floating-point numbers are large enough to make exponent overflow very remote, and thus, exponent overflow is neglected. The exponents are connected to a magnitude comparator that provides three binary outputs to indicate their relative magnitude.

### Fraction Representation

The numbers in the mantissa are treated as fractions, with the binary point assumed to reside to the left of the magnitude part. This approach is chosen to avoid scaling problems during multiplication and division. The assumption is made that all floating-point operands are initially normalized and will be normalized after each arithmetic operation.
## Decimal Arithmetic Unit
## Decimal Arithmetic Operations