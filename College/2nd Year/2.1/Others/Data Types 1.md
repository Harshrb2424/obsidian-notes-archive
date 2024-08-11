# Data Types and Number Systems

## Data Types in Registers

- **Registers Content:**
  - Contain either data or control information.
  - Control information specifies the sequence of command signals needed for data manipulation.
  - Data includes numbers and other binary-coded information operated on.

- **Possible Data Types:**
  - Numbers for computations.
  - Letters of the alphabet for data processing.
  - Other discrete symbols for specific purposes.

- **Binary Representation:**
  - All data types, except binary numbers, are represented in binary-coded form.

## Number Systems

- **Base (Radix) r:**
  - A number system using distinct symbols for r digits.
  - Numbers represented by a string of digit symbols.

- **Example Decimal Number:**
  - The string "724.5" represents the quantity:
    - \($7 \times 10^2 + 2 \times 10^1 + 4 \times 10^0 + 5 \times 10^{-1}$\).

- **Example Binary Number:**
  - The binary string "101101" represents the quantity:
    - \($1 \times 2^5 + 0 \times 2^4 + 1 \times 2^3 + 1 \times 2^2 + 0 \times 2^1 + 1 \times 2^0 = 45$\).
  - \($(101101)_2 = (45)_{10}$\).

- **Other Number Systems:**
  - Octal (Radix 8): \( $(736.4)_8 = 7 \times 8^2 + 3 \times 8^1 + 6 \times 8^0 + 4 \times 8^{-1} = (478.5)_{10}$ \).
  - Hexadecimal (Radix 16): \( $(F3)_{16} = F \times 16^1 + 3 \times 16^0 = (243)_{10}$ \).

- **Conversion:**
  - From decimal to radix r system involves separating the number into integer and fraction parts.
  - Integer: Divide successively by r and accumulate remainders.
  - Fraction: Multiply successively by r until the fraction becomes zero.

- **Octal and Hexadecimal:**
  - Each octal digit corresponds to three binary digits.
  - Each hexadecimal digit corresponds to four binary digits, reducing the number of digits by 1/3 or 1/4, respectively.

## Binary Codes

- **Binary Code:**
  - Group of n bits that assume up to \(2^n\) distinct combinations.
  - A four-bit code is necessary to represent the ten decimal digits, with 6 unused combinations.

- **Binary-Coded Decimal (BCD):**
  - Represents decimal digits directly.
  - Example: Decimal 99 is represented in binary as "1100011" but in BCD as "1001 1001".

## Alphanumeric Binary Codes

- **ASCII (American Standard Code for Information Interchange):**
  - Standard alphanumeric binary code using seven bits to code 128 characters.

- **Purpose of Binary Codes:**
  - Necessary for registers, which can hold binary information only.