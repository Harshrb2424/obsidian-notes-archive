# History of C Language

> **Dennis Ritchie**: The C programming language was developed by Dennis Ritchie at Bell Laboratories.

- **Bell Laboratories (Bell Labs)**: Located in Murray Hill, New Jersey, Bell Labs is a historic research and scientific development company.
- **1972**: The development of C began in 1972 as an evolution of the B language, which was itself derived from the BCPL (Basic Combined Programming Language).
- **C18 (ISO/IEC 9899:2018)**: The latest standard of the C language, known as C18, was published in June 2018. It is a minor revision of the previous standard, C11, with clarifications and corrections.

- **BCPL**: Created by Martin Richards in 1966, BCPL influenced the development of B.
- **B Language**: Developed by Ken Thompson at Bell Labs, B was the direct predecessor of C.
- **Assembly Language**: The syntax and structure of C were designed to be close to machine-level programming, providing efficient execution.

## Why Learn C Language?

1. **Foundation of Modern Programming**: Understanding C provides a strong foundation for learning other programming languages like C++, Java, and Python, as many concepts in these languages are derived from C.
2. **System Programming**: C is widely used for developing system software, including operating systems, embedded systems, and hardware drivers.
3. **Performance**: Programs written in C are highly efficient and can run on various hardware platforms, making it ideal for performance-critical applications.
4. **Portability**: C code is portable, meaning programs written in C can be compiled and run on many different types of computers with little or no modification.
5. **Extensive Use in Industry**: Many legacy systems, databases, and applications are written in C, and knowledge of C is essential for maintaining and updating these systems.
6. **Open Source Projects**: Many influential open-source projects like the Linux kernel and the Python interpreter are written in C, offering opportunities for learning and contributing to important software.

# Constants

In C, constants refer to fixed values that do not change during the execution of a program. Constants can be of several types:

1. **Literal Constants**: These are fixed values assigned directly in the code.

   - **Integer Constants**: Numbers without a decimal point. Example: `10`, `-5`
   - **Floating-point Constants**: Numbers with a decimal point. Example: `3.14`, `-0.001`
   - **Character Constants**: Single characters enclosed in single quotes. Example: `'A'`, `'9'`
   - **String Constants**: Sequences of characters enclosed in double quotes. Example: `"Hello"`, `"C Programming"`

2. **Symbolic Constants**: Defined using the `#define` preprocessor directive or the `const` keyword.
   - **Using `#define`**:
     ```c
     #define PI 3.14159
     #define MAX_SIZE 100
     ```
   - **Using `const`**:
     ```c
     const int MAX_SIZE = 100;
     const float PI = 3.14159;
     ```

# Data Types

> C provides a variety of data types to store different kinds of data. These are categorized into basic, derived, enumeration, and void types.

1. **Basic Data Types**

   - **Integer Types**: Used to store whole numbers.

     - `int`: Standard integer type. Example: `int a = 10;`
     - `short`: Short integer type. Example: `short b = 5;`
     - `long`: Long integer type. Example: `long c = 1234567890;`
     - `long long`: Extended long integer type. Example: `long long d = 1234567890123456789;`
     - `unsigned`: Modifier to store only non-negative values. Example: `unsigned int e = 100;`

   - **Floating-point Types**: Used to store real numbers.

     - `float`: Single precision floating-point. Example: `float x = 3.14f;`
     - `double`: Double precision floating-point. Example: `double y = 3.1415926535;`
     - `long double`: Extended precision floating-point. Example: `long double z = 3.14159265358979323846;`

   - **Character Types**: Used to store single characters.
     - `char`: Single character type. Example: `char ch = 'A';`
     - `unsigned char`: Non-negative character type. Example: `unsigned char uch = 255;`
     - `signed char`: Explicitly signed character type. Example: `signed char sch = -128;`

2. **Derived Data Types**

   - **Arrays**: Collection of elements of the same type. Example: `int arr[10];`
   - **Pointers**: Variables that store memory addresses. Example: `int *p;`
   - **Structures**: Collection of variables of different types. Example:
     ```c
     struct Point {
         int x;
         int y;
     };
     struct Point p1;
     ```
   - **Unions**: Similar to structures but share the same memory location. Example:
     ```c
     union Data {
         int i;
         float f;
         char str[20];
     };
     union Data data;
     ```

3. **Enumeration Data Types**

   - **Enums**: User-defined type consisting of named integer constants. Example:
     ```c
     enum Color { RED, GREEN, BLUE };
     enum Color c = RED;
     ```

4. **Void Type**
   - **Void**: Represents the absence of type. Used for functions that do not return a value. Example:
     ```c
     void printMessage() {
         printf("Hello, World!");
     }
     ```

Understanding constants and data types in C is crucial for effective programming, as they define how data is stored and manipulated in a program.

# The `printf` Function in C

> The `printf` function is a part of the C standard library and is used to output formatted text to the standard output (typically the console).

1. **Basic Syntax**:

   ```c
   printf("format string", arguments);
   ```

   - **Format string**: A string containing text and format specifiers.
   - **Arguments**: Variables or values to be formatted and printed according to the format specifiers.

2. **Common Format Specifiers**:

   - `%d` or `%i`: Signed integer. Example: `printf("%d", 42);`
   - `%u`: Unsigned integer. Example: `printf("%u", 42);`
   - `%f`: Floating-point number. Example: `printf("%f", 3.14);`
   - `%lf`: Double precision floating-point number. Example: `printf("%lf", 3.1415926535);`
   - `%c`: Single character. Example: `printf("%c", 'A');`
   - `%s`: String. Example: `printf("%s", "Hello");`
   - `%x` or `%X`: Unsigned hexadecimal integer. Example: `printf("%x", 255);`
   - `%o`: Unsigned octal integer. Example: `printf("%o", 255);`
   - `%%`: Literal percent sign. Example: `printf("%%");`

3. **Examples**:

   ```c
   int age = 25;
   float pi = 3.14159;
   char initial = 'J';
   char name[] = "Alice";

   printf("Age: %d\n", age);
   printf("Value of Pi: %.2f\n", pi); // Limits to 2 decimal places
   printf("Initial: %c\n", initial);
   printf("Name: %s\n", name);
   ```

4. **Format Specifier Modifiers**:
   - **Width and Precision**: Control the minimum width and number of decimal places.
     ```c
     printf("%10d", 123);  // Prints "       123"
     printf("%.3f", 3.14159);  // Prints "3.142"
     ```
   - **Flags**:
     - `-`: Left-align the output. Example: `printf("%-10d", 123);`
     - `0`: Pad with zeros instead of spaces. Example: `printf("%010d", 123);`

### How Not to Use `printf`

1. **Mismatched Format Specifiers and Arguments**:

   - Using the wrong format specifier for the data type can cause undefined behavior.
     ```c
     int num = 100;
     printf("%f", num);  // Incorrect: %f expects a float, but num is an int
     ```

2. **Insufficient Arguments**:

   - Not providing enough arguments for the format specifiers.
     ```c
     printf("%d %d", 10);  // Incorrect: Only one argument provided, but two specifiers
     ```

3. **Excess Arguments**:

   - Providing more arguments than there are format specifiers.
     ```c
     printf("%d", 10, 20);  // Incorrect: Only one specifier, but two arguments
     ```

4. **Unescaped Percent Signs**:

   - Using `%` without escaping it as `%%`.
     ```c
     printf("100% complete");  // Incorrect: % should be escaped as %%
     printf("100%% complete");  // Correct
     ```

5. **Buffer Overflows**:

   - Not considering the buffer size for strings can lead to overflows.
     ```c
     char str[10];
     sprintf(str, "%s", "This is a very long string");  // Potential overflow
     ```

6. **Uninitialized Variables**:

   - Printing uninitialized variables can lead to unpredictable output.
     ```c
     int uninitVar;
     printf("%d", uninitVar);  // Incorrect: uninitVar is not initialized
     ```

7. **Always Match Types**: Ensure the type of each argument matches its corresponding format specifier.
8. **Use Precision and Width**: Format the output to improve readability.
9. **Check Buffer Sizes**: When using functions like `sprintf`, ensure the buffer is large enough.
10. **Escape Special Characters**: Properly escape characters like `%` when necessary.
11. **Initialize Variables**: Always initialize variables before using them in `printf`.

# Operators in C

Operators are special symbols used to perform operations on variables and values. They are categorized based on the type of operations they perform.

## Arithmetic Operators

> Arithmetic operators are used to perform basic mathematical operations.

1. **Addition (`+`)**:

   - Adds two operands.
   - Example: `a + b`
     ```c
     int a = 10, b = 5;
     int result = a + b; // result is 15
     ```

2. **Subtraction (`-`)**:

   - Subtracts the second operand from the first.
   - Example: `a - b`
     ```c
     int a = 10, b = 5;
     int result = a - b; // result is 5
     ```

3. **Multiplication (`*`)**:

   - Multiplies two operands.
   - Example: `a * b`
     ```c
     int a = 10, b = 5;
     int result = a * b; // result is 50
     ```

4. **Division (`/`)**:

   - Divides the first operand by the second. For integers, it returns the quotient.
   - Example: `a / b`
     ```c
     int a = 10, b = 5;
     int result = a / b; // result is 2
     float x = 5.0, y = 2.0;
     float result_float = x / y; // result is 2.5
     ```

5. **Modulus (`%`)**:

   - Returns the remainder of the division of the first operand by the second. Applicable to integer operands only.
   - Example: `a % b`
     ```c
     int a = 10, b = 3;
     int result = a % b; // result is 1
     ```

6. **Increment (`++`)**:

   - Increases an integer value by one.
   - Example: `++a` (prefix) or `a++` (postfix)
     ```c
     int a = 10;
     ++a; // a is now 11
     a++; // a is now 12
     ```

7. **Decrement (`--`)**:
   - Decreases an integer value by one.
   - Example: `--a` (prefix) or `a--` (postfix)
     ```c
     int a = 10;
     --a; // a is now 9
     a--; // a is now 8
     ```

## Relational Operators

> Relational operators are used to compare two values. They return either `true` (non-zero) or `false` (zero).

1. **Equal to (`==`)**:

   - Checks if two operands are equal.
   - Example: `a == b`
     ```c
     int a = 10, b = 10;
     if (a == b) {
         // This block will execute
     }
     ```

2. **Not equal to (`!=`)**:

   - Checks if two operands are not equal.
   - Example: `a != b`
     ```c
     int a = 10, b = 5;
     if (a != b) {
         // This block will execute
     }
     ```

3. **Greater than (`>`)**:

   - Checks if the first operand is greater than the second.
   - Example: `a > b`
     ```c
     int a = 10, b = 5;
     if (a > b) {
         // This block will execute
     }
     ```

4. **Less than (`<`)**:

   - Checks if the first operand is less than the second.
   - Example: `a < b`
     ```c
     int a = 5, b = 10;
     if (a < b) {
         // This block will execute
     }
     ```

5. **Greater than or equal to (`>=`)**:

   - Checks if the first operand is greater than or equal to the second.
   - Example: `a >= b`
     ```c
     int a = 10, b = 10;
     if (a >= b) {
         // This block will execute
     }
     ```

6. **Less than or equal to (`<=`)**:
   - Checks if the first operand is less than or equal to the second.
   - Example: `a <= b`
     ```c
     int a = 5, b = 10;
     if (a <= b) {
         // This block will execute
     }
     ```

## Logical Operators

> Logical operators are used to combine conditional statements. They return either `true` (non-zero) or `false` (zero).

1. **Logical AND (`&&`)**:

   - Returns `true` if both operands are `true`.
   - Example: `a && b`
     ```c
     int a = 1; // true
     int b = 0; // false
     if (a && b) {
         // This block will not execute because b is false
     }
     ```

2. **Logical OR (`||`)**:

   - Returns `true` if at least one of the operands is `true`.
   - Example: `a || b`
     ```c
     int a = 1; // true
     int b = 0; // false
     if (a || b) {
         // This block will execute because a is true
     }
     ```

3. **Logical NOT (`!`)**:
   - Returns `true` if the operand is `false`, and `false` if the operand is `true`.
   - Example: `!a`
     ```c
     int a = 1; // true
     if (!a) {
         // This block will not execute because a is true
     }
     int b = 0; // false
     if (!b) {
         // This block will execute because b is false
     }
     ```

## Bitwise Operators

> Bitwise operators perform operations on the binary representations of integers.

1. **Bitwise AND (`&`)**:

   - Performs a logical AND operation on each bit of the operands.
   - Example: `a & b`
     ```c
     int a = 5; // binary: 0101
     int b = 3; // binary: 0011
     int result = a & b; // result is 1 (binary: 0001)
     ```

2. **Bitwise OR (`|`)**:

   - Performs a logical OR operation on each bit of the operands.
   - Example: `a | b`
     ```c
     int a = 5; // binary: 0101
     int b = 3; // binary: 0011
     int result = a | b; // result is 7 (binary: 0111)
     ```

3. **Bitwise XOR (`^`)**:

   - Performs a logical XOR operation on each bit of the operands.
   - Example: `a ^ b`
     ```c
     int a = 5; // binary: 0101
     int b = 3; // binary: 0011
     int result = a ^ b; // result is 6 (binary: 0110)
     ```

4. **Bitwise NOT (`~`)**:

   - Inverts each bit of the operand (also known as one’s complement).
   - Example: `~a`
     ```c
     int a = 5; // binary: 0101
     int result = ~a; // result is -6 (binary: 1010 in two's complement form)
     ```

5. **Bitwise Left Shift (`<<`)**:

   - Shifts the bits of the first operand to the left by the number of positions specified by the second operand.
   - Example: `a << b`
     ```c
     int a = 5; // binary: 0101
     int result = a << 1; // result is 10 (binary: 1010)
     ```

6. **Bitwise Right Shift (`>>`)**:
   - Shifts the bits of the first operand to the right by the number of positions specified by the second operand.
   - Example: `a >> b`
     ```c
     int a = 5; // binary: 0101
     int result = a >> 1; // result is 2 (binary: 0010)
     ```

## Assignment Operators

> Assignment operators are used to assign values to variables. The most basic assignment operator is `=`, but there are also compound assignment operators that combine arithmetic operations with assignment.

1. **Basic Assignment (`=`)**:

   - Assigns the value of the right operand to the left operand.
   - Example: `a = b`
     ```c
     int a;
     int b = 10;
     a = b; // a is now 10
     ```

2. **Compound Assignment Operators**:

   - Combine an arithmetic operation with assignment.
   - Examples:

     ```c
     int a = 5;

     a += 3; // equivalent to a = a + 3; a is now 8
     a -= 2; // equivalent to a = a - 2; a is now 6
     a *= 4; // equivalent to a = a * 4; a is now 24
     a /= 3; // equivalent to a = a / 3; a is now 8
     a %= 5; // equivalent to a = a % 5; a is now 3
     a &= 2; // equivalent to a = a & 2;
     a |= 1; // equivalent to a = a | 1;
     a ^= 1; // equivalent to a = a ^ 1;
     a <<= 1; // equivalent to a = a << 1;
     a >>= 1; // equivalent to a = a >> 1;
     ```

## Other Operators

1. **`sizeof` Operator**:

   - Returns the size, in bytes, of its operand.
   - Example:
     ```c
     int a = 10;
     printf("Size of int: %zu\n", sizeof(int)); // typically outputs 4
     printf("Size of a: %zu\n", sizeof(a)); // typically outputs 4
     ```

2. **Comma Operator (`,`)**:

   - Allows two expressions to be evaluated in a single statement. The value of the comma expression is the value of the second expression.
   - Example:
     ```c
     int a, b, c;
     a = (b = 3, c = b + 2); // b is 3, c is 5, a is 5
     ```

3. **Conditional Operator (`?:`)**:

   - Ternary operator that returns one of two values depending on the condition.
   - Example:
     ```c
     int a = 10, b = 20;
     int max = (a > b) ? a : b; // max is 20
     ```

4. **Dot (`.`) and Arrow (`->`) Operators**:

   - **Dot (`.`)**: Accesses members of a structure or union.
     ```c
     struct Point {
         int x;
         int y;
     };
     struct Point p = {1, 2};
     int x = p.x; // x is 1
     ```
   - **Arrow (`->`)**: Accesses members of a structure or union through a pointer.
     ```c
     struct Point {
         int x;
         int y;
     };
     struct Point *p = {1, 2};
     int x = p->x; // x is 1
     ```

5. **Address-of (`&`) and Dereference (`*`) Operators**:

   - **Address-of (`&`)**: Returns the memory address of a variable.
     ```c
     int a = 10;
     int *ptr = &a; // ptr now holds the address of a
     ```
   - **Dereference (`*`)**: Accesses the value at a given address.
     ```c
     int a = 10;
     int *ptr = &a;
     int value = *ptr; // value is 10
     ```

6. **Unary, Binary, and Ternary Operators**:

   - **Unary Operators**: Operate on a single operand.

     - Examples: `+`, `-`, `!`, `~`, `++`, `--`, `&`, `*`

     ```c
     int a = 5;
     int b = -a; // Unary minus, b is -5
     int c = !a; // Logical NOT, c is 0 (false)
     ```

   - **Binary Operators**: Operate on two operands.

     - Examples: `+`, `-`, `*`, `/`, `%`, `&&`, `||`, `&`, `|`, `^`, `<<`, `>>`

     ```c
     int a = 5, b = 3;
     int sum = a + b; // sum is 8
     int and = a & b; // bitwise AND, and is 1
     ```

   - **Ternary Operator**: Operates on three operands.
     - Example: `?:`
     ```c
     int a = 10, b = 20;
     int max = (a > b) ? a : b; // max is 20
     ```

# Operator Precedence and Associativity in C

Operator precedence and associativity determine the order in which operators are evaluated in expressions. Operators with higher precedence are evaluated before operators with lower precedence. When operators have the same precedence, associativity determines the order of evaluation.

| Precedence Level | Operator                                            | Description                                                                                                          | Associativity |
| ---------------- | --------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | ------------- |
| 1                | `()` `[]` `->` `.`                                  | Function call, array subscripting, member access via pointer, member access                                          | Left to Right |
| 2                | `!` `~` `++` `--` `+` `-` `*` `&` `sizeof` `(type)` | Logical NOT, bitwise NOT, increment, decrement, unary plus, unary minus, dereference, address-of, size of, type cast | Right to Left |
| 3                | `*` `/` `%`                                         | Multiplication, division, modulus                                                                                    | Left to Right |
| 4                | `+` `-`                                             | Addition, subtraction                                                                                                | Left to Right |
| 5                | `<<` `>>`                                           | Bitwise shift left, bitwise shift right                                                                              | Left to Right |
| 6                | `<` `<=` `>` `>=`                                   | Relational less than, less than or equal to, greater than, greater than or equal to                                  | Left to Right |
| 7                | `==` `!=`                                           | Equality, inequality                                                                                                 | Left to Right |
| 8                | `&`                                                 | Bitwise AND                                                                                                          | Left to Right |
| 9                | `^`                                                 | Bitwise XOR                                                                                                          | Left to Right |
| 10               |                                                     | Bitwise OR                                                                                                           | Left to Right |
| 11               | `&&`                                                | Logical AND                                                                                                          | Left to Right |
| 12               |                                                     | Logical OR                                                                                                           | Left to Right |
| 13               | `?:`                                                | Conditional (ternary)                                                                                                | Right to Left |
| 14               | `=` `+=` `-=` `*=` `/=` `%=` `<<=` `>>=` `&=` `^=`  | Assignment and compound assignment                                                                                   | Right to Left |
| 15               | `,`                                                 | Comma                                                                                                                | Left to Right |

1. **Highest Precedence**: Parentheses `()`, array subscripting `[]`, member access `.` and `->` have the highest precedence and are evaluated first, from left to right.
2. **Unary Operators**: Unary operators like `!`, `~`, `++`, `--`, and type casting `(type)` have high precedence and are evaluated from right to left.
3. **Arithmetic Operators**: Multiplication `*`, division `/`, and modulus `%` have higher precedence than addition `+` and subtraction `-`.
4. **Relational and Equality Operators**: Relational operators (`<`, `<=`, `>`, `>=`) have higher precedence than equality operators (`==`, `!=`).
5. **Logical Operators**: Logical AND `&&` has higher precedence than logical OR `||`.
6. **Conditional Operator**: The ternary conditional operator `?:` has right-to-left associativity.
7. **Assignment Operators**: Assignment `=` and compound assignment operators (`+=`, `-=`, etc.) have right-to-left associativity and are among the lowest in precedence.
8. **Comma Operator**: The comma operator `,` has the lowest precedence and is evaluated last.

# Control Structures in C

> Control structures are used to determine the flow of execution in a program. The primary control structures in C are `if`, `if-else`, `if-else if-else`, `nested if`, and `switch`.

## 1. `if` Statement

> **Definition**: The `if` statement is used to execute a block of code if a specified condition is true.

**Syntax**:

```c
if (condition) {
    // Code to execute if the condition is true
}
```

**Example**:

```c
#include <stdio.h>

int main() {
    int num = 10;

    if (num > 0) {
        printf("The number is positive.\n");
    }

    return 0;
}
```

## 2. `if-else` Statement

> **Definition**: The `if-else` statement executes one block of code if a condition is true, and another block if the condition is false.

**Syntax**:

```c
if (condition) {
    // Code to execute if the condition is true
} else {
    // Code to execute if the condition is false
}
```

**Example**:

```c
#include <stdio.h>

int main() {
    int num = -5;

    if (num > 0) {
        printf("The number is positive.\n");
    } else {
        printf("The number is negative.\n");
    }

    return 0;
}
```

## 3. `if-else if-else` Statement

> **Definition**: The `if-else if-else` statement checks multiple conditions, executing the block of code for the first true condition.

**Syntax**:

```c
if (condition1) {
    // Code to execute if condition1 is true
} else if (condition2) {
    // Code to execute if condition2 is true
} else {
    // Code to execute if none of the above conditions are true
}
```

**Example**:

```c
#include <stdio.h>

int main() {
    int num = 0;

    if (num > 0) {
        printf("The number is positive.\n");
    } else if (num < 0) {
        printf("The number is negative.\n");
    } else {
        printf("The number is zero.\n");
    }

    return 0;
}
```

## 4. Nested `if` Statement

> **Definition**: A nested `if` statement is an `if` statement inside another `if` or `else` statement.

**Syntax**:

```c
if (condition1) {
    if (condition2) {
        // Code to execute if both condition1 and condition2 are true
    }
}
```

**Example**:

```c
#include <stdio.h>

int main() {
    int num = 5;

    if (num >= 0) {
        if (num == 0) {
            printf("The number is zero.\n");
        } else {
            printf("The number is positive.\n");
        }
    } else {
        printf("The number is negative.\n");
    }

    return 0;
}
```

## 5. `switch` Statement

> **Definition**: The `switch` statement selects one of many code blocks to be executed based on the value of a variable or expression.

**Syntax**:

```c
switch (expression) {
    case constant1:
        // Code to execute if expression equals constant1
        break;
    case constant2:
        // Code to execute if expression equals constant2
        break;
    // More cases...
    default:
        // Code to execute if expression does not match any case
}
```

**Example**:

```c
#include <stdio.h>

int main() {
    int day = 3;

    switch (day) {
        case 1:
            printf("Monday\n");
            break;
        case 2:
            printf("Tuesday\n");
            break;
        case 3:
            printf("Wednesday\n");
            break;
        case 4:
            printf("Thursday\n");
            break;
        case 5:
            printf("Friday\n");
            break;
        case 6:
            printf("Saturday\n");
            break;
        case 7:
            printf("Sunday\n");
            break;
        default:
            printf("Invalid day\n");
    }

    return 0;
}
```

# Programs

**1 . Question**: Write a program to input two integers from the user and compute their sum.

```c
#include <stdio.h>

int main() {
    int num1, num2, sum;

    // Input two integers
    printf("Enter first number: ");
    scanf("%d", &num1);
    printf("Enter second number: ");
    scanf("%d", &num2);

    // Calculate sum
    sum = num1 + num2;

    // Display the result
    printf("Sum of %d and %d is %d\n", num1, num2, sum);

    return 0;
}
```

**2. Question**: Write a program to calculate the simple interest for a given principal amount, rate of interest, and time period.

```c
#include <stdio.h>

int main() {
    float principal, rate, time, interest;

    // Input principal amount, rate, and time
    printf("Enter principal amount: ");
    scanf("%f", &principal);
    printf("Enter annual interest rate (in percentage): ");
    scanf("%f", &rate);
    printf("Enter time period (in years): ");
    scanf("%f", &time);

    // Calculate simple interest
    interest = (principal * rate * time) / 100.0;

    // Display the result
    printf("Simple Interest = %.2f\n", interest);

    return 0;
}
```

**3. Question**: Write a program to check whether a given integer is even or odd.

```c
#include <stdio.h>

int main() {
    int num;

    // Input an integer
    printf("Enter an integer: ");
    scanf("%d", &num);

    // Check if the number is even or odd
    if (num % 2 == 0) {
        printf("%d is even.\n", num);
    } else {
        printf("%d is odd.\n", num);
    }

    return 0;
}
```

**4. Question**: Write a program to input marks of a student and calculate the grade based on the following criteria:

- Marks >= 85 : Grade A
- 70 <= Marks < 85 : Grade B
- 55 <= Marks < 70 : Grade C
- 40 <= Marks < 55 : Grade D
- Marks < 40 : Grade F

```c
#include <stdio.h>

int main() {
    int marks;
    char grade;

    // Input marks
    printf("Enter marks: ");
    scanf("%d", &marks);

    // Calculate grade using switch statement
    switch (marks / 10) {
        case 10:
        case 9:
            grade = 'A';
            break;
        case 8:
        case 7:
            grade = 'B';
            break;
        case 6:
        case 5:
            grade = 'C';
            break;
        case 4:
            grade = 'D';
            break;
        default:
            grade = 'F';
    }

    // Display the grade
    printf("Grade: %c\n", grade);

    return 0;
}
```

**5. Question**: Write a program to calculate the factorial of a non-negative integer using recursion.

```c
#include <stdio.h>

// Function to calculate factorial recursively
unsigned long long factorial(int n) {
    if (n == 0 || n == 1) {
        return 1;
    } else {
        return n * factorial(n - 1);
    }
}

int main() {
    int num;

    // Input a non-negative integer
    printf("Enter a non-negative integer: ");
    scanf("%d", &num);

    // Calculate factorial and display the result
    printf("Factorial of %d = %llu\n", num, factorial(num));

    return 0;
}
```

# Looping Statements in C

> Looping statements are used to execute a block of code repeatedly as long as a specified condition is true. The primary looping constructs in C are `while`, `do-while`, and `for` loops.

## 1. `while` Loop

**Definition**: The `while` loop executes a block of code repeatedly as long as a specified condition is true.

**Syntax**:

```c
while (condition) {
    // Code to be executed repeatedly
}
```

**Example**:

```c
#include <stdio.h>

int main() {
    int i = 1;

    // Print numbers from 1 to 5 using while loop
    while (i <= 5) {
        printf("%d ", i);
        i++;
    }
    printf("\n");

    return 0;
}
```

## 2. `do-while` Loop

> **Definition**: The `do-while` loop is similar to the `while` loop, but the condition is evaluated after executing the block of code, ensuring that the block is executed at least once.

**Syntax**:

```c
do {
    // Code to be executed repeatedly
} while (condition);
```

**Example**:

```c
#include <stdio.h>

int main() {
    int i = 1;

    // Print numbers from 1 to 5 using do-while loop
    do {
        printf("%d ", i);
        i++;
    } while (i <= 5);
    printf("\n");

    return 0;
}
```

## 3. `for` Loop

> **Definition**: The `for` loop executes a block of code repeatedly for a specified number of times, or while a specified condition is true.

**Syntax**:

```c
for (initialization; condition; increment/decrement) {
    // Code to be executed repeatedly
}
```

**Example**:

```c
#include <stdio.h>

int main() {
    // Print numbers from 1 to 5 using for loop
    for (int i = 1; i <= 5; i++) {
        printf("%d ", i);
    }
    printf("\n");

    return 0;
}
```

- **`while` loop**: Executes a block of code repeatedly as long as a condition is true.
- **`do-while` loop**: Executes a block of code repeatedly at least once, and then continues to execute as long as a condition is true.
- **`for` loop**: Executes a block of code repeatedly for a specified number of times, controlled by an initialization, condition, and increment/decrement.

In C programming, `break`, `continue`, and `exit` are control statements that alter the flow of execution within loops or functions. Here's how each of them works:

### 1. `break` Statement

> **Definition**: The `break` statement is used to terminate the nearest enclosing loop (`for`, `while`, `do-while`) or `switch` statement immediately when encountered.

**Usage**: It is typically used to exit a loop prematurely based on certain conditions.

**Example**:

```c
#include <stdio.h>

int main() {
    // Print numbers from 1 to 5 but break the loop when i is 3
    for (int i = 1; i <= 5; i++) {
        if (i == 3) {
            break; // Exit the loop when i is 3
        }
        printf("%d ", i);
    }
    printf("\n");

    return 0;
}
```

Output:

```
1 2
```

### 2. `continue` Statement

> **Definition**: The `continue` statement skips the rest of the current iteration of a loop and jumps to the next iteration, ignoring any subsequent code within the loop for that particular iteration.

**Usage**: It is used to skip over specific iterations of a loop based on certain conditions without terminating the entire loop.

**Example**:

```c
#include <stdio.h>

int main() {
    // Print numbers from 1 to 5 but skip printing when i is 3
    for (int i = 1; i <= 5; i++) {
        if (i == 3) {
            continue; // Skip iteration when i is 3
        }
        printf("%d ", i);
    }
    printf("\n");

    return 0;
}
```

Output:

```
1 2 4 5
```

### 3. `exit` Function

> **Definition**: The `exit` function is used to terminate the program immediately and return control to the operating system. It can be found in the `stdlib.h` header file.

**Usage**: It is often used to handle abnormal terminations or to terminate the program based on certain conditions.

**Example**:

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int num;

    while (1) {
        printf("Enter a number (enter 0 to exit): ");
        scanf("%d", &num);

        if (num == 0) {
            exit(0); // Exit the program if num is 0
        }

        // Otherwise, continue processing
        printf("You entered: %d\n", num);
    }

    return 0;
}
```

In this example, entering `0` will terminate the program immediately.

- **`break`**: Terminates the nearest enclosing loop or `switch` statement.
- **`continue`**: Skips the current iteration of a loop and continues with the next iteration.
- **`exit`**: Terminates the entire program and returns control to the operating system.

# Programs

**6. Question**: Write a program to calculate the sum of natural numbers up to a given number `n` using a `while` loop.

```c
#include <stdio.h>

int main() {
    int n, sum = 0, i = 1;

    // Input the number n
    printf("Enter a positive integer n: ");
    scanf("%d", &n);

    // Calculate sum of natural numbers from 1 to n using while loop
    while (i <= n) {
        sum += i;
        i++;
    }

    // Display the sum
    printf("Sum of first %d natural numbers = %d\n", n, sum);

    return 0;
}
```

**7. Question**: Write a program to calculate the factorial of a non-negative integer `num` using a `for` loop.

```c
#include <stdio.h>

int main() {
    int num;
    unsigned long long factorial = 1;

    // Input a non-negative integer
    printf("Enter a non-negative integer: ");
    scanf("%d", &num);

    // Calculate factorial using for loop
    for (int i = 1; i <= num; i++) {
        factorial *= i;
    }

    // Display the factorial
    printf("Factorial of %d = %llu\n", num, factorial);

    return 0;
}
```

**8. Question**: Write a program to print the multiplication table (up to 10) of a given number `num` using a `do-while` loop.

```c
#include <stdio.h>

int main() {
    int num, i = 1;

    // Input the number for which multiplication table is to be printed
    printf("Enter a number: ");
    scanf("%d", &num);

    // Print multiplication table using do-while loop
    do {
        printf("%d x %d = %d\n", num, i, num * i);
        i++;
    } while (i <= 10);

    return 0;
}
```

**9. Question**: Write a program to print all even numbers between 1 and 20, skipping odd numbers using `continue` statement.

```c
#include <stdio.h>

int main() {
    // Print even numbers between 1 and 20, skipping odd numbers using continue
    for (int i = 1; i <= 20; i++) {
        if (i % 2 != 0) {
            continue; // Skip odd numbers
        }
        printf("%d ", i);
    }
    printf("\n");

    return 0;
}
```

**10. Question**: Write a program to find all prime numbers between 1 and 50 using nested loops and `break` statement.

```c
#include <stdio.h>
#include <stdbool.h>

int main() {
    // Print prime numbers between 1 and 50 using nested loops and break
    for (int i = 2; i <= 50; i++) {
        bool is_prime = true;

        // Check if i is a prime number
        for (int j = 2; j <= i / 2; j++) {
            if (i % j == 0) {
                is_prime = false;
                break; // Exit the inner loop if i is not prime
            }
        }

        // Print i if it is a prime number
        if (is_prime) {
            printf("%d ", i);
        }
    }
    printf("\n");

    return 0;
}
```

# Arrays in C

> Arrays in C are a collection of elements of the same data type that are stored in contiguous memory locations. They provide a convenient way to store and manipulate data efficiently.

## 1. One-Dimensional Arrays

**Definition**: A one-dimensional array is a linear collection of elements of the same data type.

**Declaration Syntax**:

```c
type array_name[size];
```

**Example**:

```c
#include <stdio.h>

int main() {
    // Declaration and initialization of a one-dimensional array
    int marks[5] = {80, 75, 90, 85, 88};

    // Accessing elements of the array
    printf("Marks: ");
    for (int i = 0; i < 5; i++) {
        printf("%d ", marks[i]);
    }
    printf("\n");

    return 0;
}
```

## 2. Two-Dimensional Arrays

**Definition**: A two-dimensional array is an array of one-dimensional arrays, forming a grid of elements.

**Declaration Syntax**:

```c
type array_name[row_size][column_size];
```

**Example**:

```c
#include <stdio.h>

int main() {
    // Declaration and initialization of a two-dimensional array
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    // Accessing elements of the array
    printf("Matrix:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d\t", matrix[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

## 3. Multi-Dimensional Arrays

**Definition**: Multi-dimensional arrays in C are arrays with more than two dimensions. They extend the concept of two-dimensional arrays to higher dimensions.

**Declaration Syntax**:

```c
type array_name[dim1_size][dim2_size]...[dimN_size];
```

**Example** (3D Array):

```c
#include <stdio.h>

int main() {
    // Declaration and initialization of a three-dimensional array
    int cube[3][3][3] = {
        {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}},
        {{10, 11, 12}, {13, 14, 15}, {16, 17, 18}},
        {{19, 20, 21}, {22, 23, 24}, {25, 26, 27}}
    };

    // Accessing elements of the array
    printf("Cube:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            for (int k = 0; k < 3; k++) {
                printf("%d ", cube[i][j][k]);
            }
            printf("\t"); // Separating rows for readability
        }
        printf("\n");
    }

    return 0;
}
```

# Programs

**11. Question**: Write a program to add two matrices of the same size.

```c
#include <stdio.h>

#define ROWS 3
#define COLS 3

void add_matrices(int mat1[ROWS][COLS], int mat2[ROWS][COLS], int result[ROWS][COLS]) {
    for (int i = 0; i < ROWS; i++) {
        for (int j = 0; j < COLS; j++) {
            result[i][j] = mat1[i][j] + mat2[i][j];
        }
    }
}

int main() {
    int matrix1[ROWS][COLS] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    int matrix2[ROWS][COLS] = {
        {10, 11, 12},
        {13, 14, 15},
        {16, 17, 18}
    };

    int result[ROWS][COLS];

    // Call function to add matrices
    add_matrices(matrix1, matrix2, result);

    // Display the result matrix
    printf("Matrix Addition Result:\n");
    for (int i = 0; i < ROWS; i++) {
        for (int j = 0; j < COLS; j++) {
            printf("%d\t", result[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

**12. Question**: Write a program to multiply two matrices of compatible dimensions.

```c
#include <stdio.h>

#define ROWS1 3
#define COLS1 2
#define ROWS2 2
#define COLS2 3

void multiply_matrices(int mat1[ROWS1][COLS1], int mat2[ROWS2][COLS2], int result[ROWS1][COLS2]) {
    for (int i = 0; i < ROWS1; i++) {
        for (int j = 0; j < COLS2; j++) {
            result[i][j] = 0;
            for (int k = 0; k < COLS1; k++) {
                result[i][j] += mat1[i][k] * mat2[k][j];
            }
        }
    }
}

int main() {
    int matrix1[ROWS1][COLS1] = {
        {1, 2},
        {3, 4},
        {5, 6}
    };

    int matrix2[ROWS2][COLS2] = {
        {7, 8, 9},
        {10, 11, 12}
    };

    int result[ROWS1][COLS2];

    // Call function to multiply matrices
    multiply_matrices(matrix1, matrix2, result);

    // Display the result matrix
    printf("Matrix Multiplication Result:\n");
    for (int i = 0; i < ROWS1; i++) {
        for (int j = 0; j < COLS2; j++) {
            printf("%d\t", result[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

# Functions in C

> Functions in C are a fundamental building block that allows for modular and structured programming. They encapsulate a set of instructions that can be reused throughout a program. Functions in C can be classified based on various criteria such as their definition, usage of arguments, and return type.

## Predefined Functions (Standard Library Functions)

**Definition**: Predefined functions are provided by C standard libraries, such as `stdio.h`, `stdlib.h`, `math.h`, etc. These functions are already implemented and can be used directly in a C program.

**Example**:

```c
#include <stdio.h>

int main() {
    // Example of using a predefined function
    printf("Hello, World!\n"); // printf() is a predefined function from stdio.h

    return 0;
}
```

## User-Defined Functions

**Definition**: User-defined functions are created by the programmer to perform specific tasks. They provide modularity and improve code readability by breaking down a program into smaller, manageable parts.

**Syntax**:

```c
return_type function_name(parameters) {
    // Function body (statements)
    // Optional: return statement if return_type is not void
}
```

**Example**:

```c
#include <stdio.h>

// Function prototype declaration
int add(int a, int b);

int main() {
    int num1 = 5, num2 = 10;
    int sum;

    // Function call
    sum = add(num1, num2);

    // Display the result
    printf("Sum: %d\n", sum);

    return 0;
}

// Function definition
int add(int a, int b) {
    return a + b;
}
```

## Types of Functions According to Arguments and Return Type

Functions in C can also be categorized based on their arguments and return type:

- **Function without Arguments and without Return Value (void)**:

  ```c
  void greet() {
      printf("Hello, World!\n");
  }
  ```

- **Function with Arguments and without Return Value (void)**:

  ```c
  void display(int num) {
      printf("Number: %d\n", num);
  }
  ```

- **Function without Arguments and with Return Value**:

  ```c
  int generate_random_number() {
      return rand(); // rand() function generates a random number
  }
  ```

- **Function with Arguments and with Return Value**:
  ```c
  int add(int a, int b) {
      return a + b;
  }
  ```

## Function Declaration and Definition

In C programming, functions are typically declared before they are used to ensure the compiler knows about them when they are called. Here’s the corrected version with the function `fun` declared before `main`:

```c
#include <stdio.h>

float fun(); // Function declaration

int main() {
    int s;
    s = fun();
    printf("%d", s);
    return 0;
}

float fun() { // Function definition
    return 6 ? 4 : 5;
}
```

## Function Definition After Main

If you need to define a function after `main`, you must provide a function declaration (prototype) before `main` to inform the compiler about the function's return type and parameters:

```c
#include <stdio.h>

int fun(int a, float b); // Function declaration

int main() {
    fun(4, 4.5);
    return 0;
}

int fun(int a, float b) { // Function definition
    printf("%d %f", a, b);
    return 0;
}
```

## Void Return Type and Return Value

If a function has a `void` return type, it does not return any value. However, the example provided tries to return an integer (`56`) from a `void` function, which is incorrect:

```c
#include <stdio.h>

void dileep() {
    return 56; // Incorrect: void function should not return a value
}

int main() {
    int a;
    a = dileep();
    printf("%d", a);
    return 0;
}
```

To fix this, the `dileep` function should either return `void` or return a value compatible with its declared return type.

## Storage Classes in C

C provides several storage classes (`auto`, `static`, `extern`, `register`) that define the lifetime, scope, and initial value of variables.

- **Auto**: Variables are stored in memory and initialized with garbage values each time the block is entered.
- **Static**: Variables retain their values between function calls and are initialized only once.
- **Extern**: Indicates that a variable is declared elsewhere in the program.
- **Register**: Suggests to the compiler to store the variable in a register for faster access.

Here’s an example demonstrating the usage of storage classes in C:

```c
#include <stdio.h>

int a; // Global variable with extern storage class

void storage_class() {
    auto int b = 0; // auto storage class for local variable
    static int c = 0; // static storage class for local variable
    register int d = 0; // register storage class for local variable

    printf("Auto: %d, Static: %d, Register: %d\n", b++, c++, d++);
}

int main() {
    storage_class();
    storage_class();
    storage_class();
    return 0;
}
```

## Acceptable Function Parameter Statements

Regarding the question about acceptable statements for function parameters:

```c
void fun(auto int a) {} // Not valid in C
void fun(static int a) {} // Not valid in C
void fun(extern int a) {} // Not valid in C
void fun(register int a) {} // Valid in C
```

In C, only `register` is a valid storage class specifier for function parameters.

## Recursion

Recursion in programming refers to the technique where a function calls itself directly or indirectly to solve a problem. It is particularly useful for solving problems that can be broken down into smaller, similar subproblems. Here, we'll discuss recursion theory briefly and provide examples of recursive functions in C.

Recursion involves two main parts:

1. **Base Case**: This is the terminating condition that stops the recursive calls. It defines the smallest problem that doesn't need further recursion.
2. **Recursive Case**: This is where the function calls itself with smaller or simpler inputs, progressing towards the base case.

Key points to remember:

- Recursion can be less efficient than iterative solutions due to overhead (function call stack).
- It simplifies complex problems into smaller, manageable parts.
- Recursive functions must have a base case to avoid infinite recursion.

# Programs

13. **Factorial Calculation**

```c
#include <stdio.h>

// Recursive function to calculate factorial
int factorial(int n) {
    // Base case: factorial of 0 is 1
    if (n == 0) {
        return 1;
    }
    // Recursive case: n! = n * (n-1)!
    else {
        return n * factorial(n - 1);
    }
}

int main() {
    int num = 5;
    printf("Factorial of %d is %d\n", num, factorial(num));
    return 0;
}
```

14. **Fibonacci Series**

```c
#include <stdio.h>

// Recursive function to calculate Fibonacci series
int fibonacci(int n) {
    // Base cases: Fibonacci(0) = 0, Fibonacci(1) = 1
    if (n == 0) {
        return 0;
    }
    else if (n == 1) {
        return 1;
    }
    // Recursive case: Fibonacci(n) = Fibonacci(n-1) + Fibonacci(n-2)
    else {
        return fibonacci(n - 1) + fibonacci(n - 2);
    }
}

int main() {
    int num = 6;
    printf("Fibonacci series up to %d terms:\n", num);
    for (int i = 0; i < num; i++) {
        printf("%d ", fibonacci(i));
    }
    printf("\n");
    return 0;
}
```

15. **Recursive Binary Search**

```c
#include <stdio.h>

// Recursive function to perform binary search
int binary_search(int arr[], int left, int right, int x) {
    if (right >= left) {
        int mid = left + (right - left) / 2;

        // Base case: element found at middle index
        if (arr[mid] == x) {
            return mid;
        }
        // Recursive cases: search in left or right subarray
        if (arr[mid] > x) {
            return binary_search(arr, left, mid - 1, x);
        } else {
            return binary_search(arr, mid + 1, right, x);
        }
    }
    // Base case: element not found
    return -1;
}

int main() {
    int arr[] = {2, 4, 6, 8, 10, 12, 14, 16};
    int n = sizeof(arr) / sizeof(arr[0]);
    int x = 10;
    int result = binary_search(arr, 0, n - 1, x);
    (result == -1) ? printf("Element is not present in array\n")
                   : printf("Element is present at index %d\n", result);
    return 0;
}
```

# Pointers in C

A pointer in C is a variable that stores the address of another variable. It provides a way to access and manipulate memory directly. Here's a breakdown of key concepts related to pointers:

- **Address and Pointer Syntax**:
  - The `&` operator is used to get the address of a variable.
  - Pointers are declared with `*` followed by the data type.

```c
#include <stdio.h>

int main() {
    float f = 79.3;
    printf("Address of f: %p\n", &f); // %p prints address in hexadecimal format

    int a = 10, b = 20;
    int *p = &a, *q = &b; // Pointers to int
    (*p)++; // Increment value pointed by p
    ++(*q); // Increment value pointed by q
    p = q; // p now points to where q points
    (*p)++; // Increment value pointed by p again
    ++(*q); // Increment value pointed by q again

    printf("\n%d %d", a, b); // Output: 11 22
    printf("\n%d %d", *p, *q); // Output: 22 22

    return 0;
}
```

- **Pointer Arithmetic and Operations**:
  - Arithmetic operations (`+`, `-`) are allowed on pointers to navigate through memory.
  - Pointer subtraction gives the number of elements between two addresses.

```c
int a, b, *p = &a, *q = &b;
int *r;
r = p + q; // Invalid operation: Can't add pointers
```

- **Special Pointer Types**:
  - **NULL Pointer**: Points to no memory location. Useful for indicating the end of lists or trees.

```c
int *p = NULL; // Initializing pointer to NULL
```

- **Void Pointer (Generic Pointer)**:
  - Can hold the address of any data type. Requires type casting to access the value.

```c
int i = 9;
void *vp = &i;
printf("%d\n", *(int*)vp); // Type casting to access integer value
```

- **Pointer of Pointers**:
  - A pointer that stores the address of another pointer.

```c
int a = 10;
int *ptr1 = &a;
int **ptr2 = &ptr1; // Pointer to pointer
```

- **Dynamic Memory Allocation**:
  - Functions like `malloc()` and `calloc()` allocate memory and return a void pointer (`void*`).

```c
#include <stdlib.h>

int *ptr = (int*)malloc(sizeof(int)); // Allocates memory for an integer
if (ptr == NULL) {
    printf("Memory allocation failed.\n");
} else {
    *ptr = 10; // Store value in allocated memory
    printf("Value stored at pointer location: %d\n", *ptr);
    free(ptr); // Free allocated memory
}
```

- **Wild Pointer**:

  - Points to an arbitrary memory location, often uninitialized.

- **Dangling Pointer**:
  - Points to a memory location that has been deallocated (freed).

# Programs

**16. Question**: Using Pointers to Swap Values

```c
#include <stdio.h>

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 5, y = 10;

    printf("Before swap: x = %d, y = %d\n", x, y);

    swap(&x, &y);

    printf("After swap: x = %d, y = %d\n", x, y);

    return 0;
}
```

- Demonstrates how to swap two integers using pointers.

**17. Question**: Passing Pointers to Functions

```c
#include <stdio.h>

void changeValue(int *ptr) {
    *ptr = 100; // Modifying the value at the address pointed by ptr
}

int main() {
    int num = 10;

    printf("Before function call: num = %d\n", num);

    changeValue(&num);

    printf("After function call: num = %d\n", num);

    return 0;
}
```

- Shows how to pass a pointer to a function to modify the value of a variable outside the function.

**18. Question**: Array and Pointers

```c
#include <stdio.h>

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int *ptr = arr; // Pointer to the first element of arr

    printf("Array elements using array indices:\n");
    for (int i = 0; i < 5; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    printf("Array elements using pointer:\n");
    for (int i = 0; i < 5; i++) {
        printf("%d ", *ptr);
        ptr++; // Move the pointer to the next element
    }
    printf("\n");

    return 0;
}
```

- Illustrates the use of pointers to access array elements both using array indices and pointer arithmetic.

**19. Question**: Dynamic Memory Allocation using Pointers

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr;
    int n;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    ptr = (int *)malloc(n * sizeof(int)); // Allocate memory dynamically

    if (ptr == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    printf("Enter %d elements:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &ptr[i]); // Access elements using array notation
    }

    printf("Elements entered are:\n");
    for (int i = 0; i < n; i++) {
        printf("%d ", ptr[i]); // Print elements using array notation
    }
    printf("\n");

    free(ptr); // Free dynamically allocated memory

    return 0;
}
```

- Uses dynamic memory allocation (`malloc`) to allocate memory for an array based on user input, and then frees the allocated memory (`free`) after use.

# Struct and Union in C

## Struct (Structure)

In C programming, `struct` and `union` are user-defined data types that allow you to group different variables under a single name. They are used to create more complex data structures that can hold multiple pieces of data of different types.

> **Definition**: A `struct` is a composite data type that groups together variables of possibly different types into a single unit.

**Syntax**:

```c
struct structure_name {
    // Member variables (can be of different data types)
    type member1;
    type member2;
    // ... more members
};
```

**Example**:

```c
#include <stdio.h>

// Define a struct to represent a point in 2D space
struct Point {
    int x;
    int y;
};

int main() {
    // Declare a struct variable
    struct Point p1;

    // Assign values to struct members
    p1.x = 10;
    p1.y = 20;

    // Access and print struct members
    printf("Point coordinates: (%d, %d)\n", p1.x, p1.y);

    return 0;
}
```

**Usage**:

- Structs are used to group related variables together.
- They simplify the management and manipulation of complex data.
- Struct members are accessed using the dot (`.`) operator.

## Union

> **Definition**: A `union` is similar to a `struct`, but all members share the same memory location. This means a `union` variable can hold values of only one member at a time.

**Syntax**:

```c
union union_name {
    // Member variables (can be of different data types)
    type member1;
    type member2;
    // ... more members
};
```

**Example**:

```c
#include <stdio.h>

// Define a union to represent a variable that can hold either an int or a float
union Data {
    int i;
    float f;
};

int main() {
    union Data d;

    d.i = 10;
    printf("d.i : %d\n", d.i);

    d.f = 20.0;
    printf("d.f : %f\n", d.f);

    // Notice that changing d.f affects d.i because they share the same memory space
    printf("d.i after assigning d.f : %d\n", d.i);

    return 0;
}
```

**Usage**:

- Unions are used when you need to store different types of data in the same memory location.
- They are useful in scenarios where memory efficiency is critical.
- Only one member of a union can be accessed at a time.

## Differences Between Struct and Union

1. **Memory Allocation**:

   - **Struct**: Allocates memory for each member individually.
   - **Union**: Shares memory among all members, using the memory required by the largest member.

2. **Memory Usage**:

   - **Struct**: Can hold multiple members, each with its own distinct memory space.
   - **Union**: Holds only one member's value at a time, but shares memory among all members.

3. **Accessing Members**:
   - **Struct**: Members are accessed using the dot (`.`) operator.
   - **Union**: Only one member can be accessed at a time, typically using the same member name.

# Programs

**20. Question**: Struct for Employee Details

```c
#include <stdio.h>
#include <string.h>

// Define a struct for Employee
struct Employee {
    int empID;
    char empName[50];
    float empSalary;
};

int main() {
    // Declare struct variables
    struct Employee emp1, emp2;

    // Assign values to emp1
    emp1.empID = 1;
    strcpy(emp1.empName, "John Doe");
    emp1.empSalary = 50000.0;

    // Assign values to emp2
    emp2.empID = 2;
    strcpy(emp2.empName, "Jane Smith");
    emp2.empSalary = 60000.0;

    // Print details of emp1
    printf("Employee 1 Details:\n");
    printf("ID: %d\n", emp1.empID);
    printf("Name: %s\n", emp1.empName);
    printf("Salary: %.2f\n", emp1.empSalary);
    printf("\n");

    // Print details of emp2
    printf("Employee 2 Details:\n");
    printf("ID: %d\n", emp2.empID);
    printf("Name: %s\n", emp2.empName);
    printf("Salary: %.2f\n", emp2.empSalary);

    return 0;
}
```

- demonstrates using a `struct` to store employee details such as ID, name, and salary for multiple employees.

**21. Question**: Struct for Point in 3D Space

```c
#include <stdio.h>

// Define a struct for Point in 3D space
struct Point3D {
    int x;
    int y;
    int z;
};

int main() {
    // Declare a struct variable
    struct Point3D p1 = {1, 2, 3};

    // Access and print struct members
    printf("Coordinates of Point p1:\n");
    printf("x: %d\n", p1.x);
    printf("y: %d\n", p1.y);
    printf("z: %d\n", p1.z);

    return 0;
}
```

- shows using a `struct` to represent a point in 3D space with coordinates x, y, and z.

**22. Question**: Union for Handling Different Data Types

```c
#include <stdio.h>

// Define a union to handle different data types
union Data {
    int i;
    float f;
    char str[20];
};

int main() {
    union Data data;

    data.i = 10;
    printf("Data.i : %d\n", data.i);

    data.f = 220.5;
    printf("Data.f : %f\n", data.f);

    strcpy(data.str, "C Programming");
    printf("Data.str : %s\n", data.str);

    // Accessing all members of the union
    printf("\nUnion Data Values:\n");
    printf("Integer: %d\n", data.i);
    printf("Float: %f\n", data.f);
    printf("String: %s\n", data.str);

    return 0;
}
```

- uses a `union` to handle different data types (`int`, `float`, `char array`) in the same memory location, showing how changing one member affects others.

**23. Question**: Union for Efficient Memory Usage

```c
#include <stdio.h>

// Define a union for storing sizes
union Sizes {
    int intSize;
    float floatSize;
    double doubleSize;
};

int main() {
    union Sizes size;

    size.intSize = sizeof(int);
    printf("Size of int: %d bytes\n", size.intSize);

    size.floatSize = sizeof(float);
    printf("Size of float: %d bytes\n", size.floatSize);

    size.doubleSize = sizeof(double);
    printf("Size of double: %d bytes\n", size.doubleSize);

    return 0;
}
```

- illustrates using a `union` to efficiently store and access sizes of different data types (`int`, `float`, `double`) in a single variable.

# Data Structures:

## Linked Lists

> Linked lists are fundamental data structures in computer science that store a collection of elements where each element (node) points to the next one. There are several types of linked lists commonly used, each with unique properties and advantages. Here, I'll cover single linked list, double linked list, and circular linked list.

### Single Linked List

In a single linked list, each node contains data and a pointer/reference to the next node in the sequence. It is simple and memory-efficient but traversal is one-way, which means you can only traverse from the head to the tail.

**Structure**:

- Each node contains two parts: data and a pointer to the next node (`next`).

**Operations**:

- **Insertion**: Inserting a node at the beginning, end, or middle of the list.
- **Deletion**: Removing a node from the list.
- **Traversal**: Iterating through the list to access or modify nodes.

**Example Code**:

```c
#include <stdio.h>
#include <stdlib.h>

// Define a structure for a node in a single linked list
struct Node {
    int data;
    struct Node* next;
};

// Function to print the linked list
void printList(struct Node* head) {
    struct Node* current = head;
    while (current != NULL) {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");
}

// Function to insert a new node at the beginning of the linked list
void insertAtBeginning(struct Node** head_ref, int new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = new_data;
    new_node->next = *head_ref;
    *head_ref = new_node;
}

int main() {
    // Initialize an empty linked list
    struct Node* head = NULL;

    // Insert nodes at the beginning
    insertAtBeginning(&head, 3);
    insertAtBeginning(&head, 7);
    insertAtBeginning(&head, 1);

    // Print the linked list
    printf("Linked List: ");
    printList(head);

    return 0;
}
```

### Double Linked List

In a double linked list, each node contains data and two pointers/references: one to the next node and another to the previous node. This allows bidirectional traversal, meaning you can traverse both forward and backward.

**Structure**:

- Each node contains three parts: data, a pointer to the next node (`next`), and a pointer to the previous node (`prev`).

**Operations**:

- **Insertion**: Inserting a node at the beginning, end, or middle of the list.
- **Deletion**: Removing a node from the list.
- **Traversal**: Iterating through the list in both directions.

### Circular Linked List

In a circular linked list, the last node points back to the first node instead of `NULL`, forming a circle. This allows traversal from any node to any other node in a circular manner.

**Structure**:

- Similar to single or double linked list, but the last node's `next` pointer points to the first node.

**Operations**:

- **Insertion**: Inserting a node at the beginning, end, or middle of the list.
- **Deletion**: Removing a node from the list.
- **Traversal**: Iterating through the list in a circular manner.

## Stack and Queue

Data structures like stacks and queues are fundamental in computer science for managing data efficiently in various algorithms and applications. Here, I'll explain each and provide example implementations in C.

### Stack

> **Definition**: A stack is a linear data structure that follows the Last In First Out (LIFO) principle, where elements are added and removed from the top only.

**Operations**:

- **Push**: Adds an element to the top of the stack.
- **Pop**: Removes the top element from the stack.
- **Peek/Top**: Returns the top element without removing it.
- **isEmpty**: Checks if the stack is empty.
- **isFull**: Checks if the stack is full (for fixed-size stacks).

**Implementation**:

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX_SIZE 100

// Define a structure for the stack
struct Stack {
    int items[MAX_SIZE];
    int top;
};

// Function to initialize the stack
void initializeStack(struct Stack* stack) {
    stack->top = -1;
}

// Function to check if the stack is full
int isFull(struct Stack* stack) {
    return stack->top == MAX_SIZE - 1;
}

// Function to check if the stack is empty
int isEmpty(struct Stack* stack) {
    return stack->top == -1;
}

// Function to push an element onto the stack
void push(struct Stack* stack, int value) {
    if (isFull(stack)) {
        printf("Stack Overflow\n");
    } else {
        stack->items[++stack->top] = value;
    }
}

// Function to pop an element from the stack
int pop(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Stack Underflow\n");
        return -1;
    } else {
        return stack->items[stack->top--];
    }
}

// Function to peek the top element of the stack
int peek(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty\n");
        return -1;
    } else {
        return stack->items[stack->top];
    }
}

int main() {
    struct Stack stack;
    initializeStack(&stack);

    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);

    printf("Top element: %d\n", peek(&stack)); // Output: 30

    printf("Elements popped from stack: %d, %d\n", pop(&stack), pop(&stack)); // Output: 30, 20

    printf("Top element after popping: %d\n", peek(&stack)); // Output: 10

    return 0;
}
```

### Queue

> **Definition**: A queue is a linear data structure that follows the First In First Out (FIFO) principle, where elements are added at the rear and removed from the front.

**Operations**:

- **Enqueue**: Adds an element to the rear of the queue.
- **Dequeue**: Removes the front element from the queue.
- **Front**: Returns the front element without removing it.
- **Rear**: Returns the rear element without removing it.
- **isEmpty**: Checks if the queue is empty.
- **isFull**: Checks if the queue is full (for fixed-size queues).

**Implementation**:

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX_SIZE 100

// Define a structure for the queue
struct Queue {
    int items[MAX_SIZE];
    int front;
    int rear;
};

// Function to initialize the queue
void initializeQueue(struct Queue* queue) {
    queue->front = -1;
    queue->rear = -1;
}

// Function to check if the queue is full
int isFull(struct Queue* queue) {
    return (queue->rear == MAX_SIZE - 1);
}

// Function to check if the queue is empty
int isEmpty(struct Queue* queue) {
    return (queue->front == -1 && queue->rear == -1);
}

// Function to add an element to the rear of the queue (enqueue)
void enqueue(struct Queue* queue, int value) {
    if (isFull(queue)) {
        printf("Queue Overflow\n");
    } else {
        if (isEmpty(queue)) {
            queue->front = 0;
        }
        queue->items[++queue->rear] = value;
    }
}

// Function to remove an element from the front of the queue (dequeue)
int dequeue(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue Underflow\n");
        return -1;
    } else {
        int removedItem = queue->items[queue->front];
        if (queue->front == queue->rear) {
            queue->front = queue->rear = -1;
        } else {
            queue->front++;
        }
        return removedItem;
    }
}

// Function to get the front element of the queue
int front(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty\n");
        return -1;
    } else {
        return queue->items[queue->front];
    }
}

// Function to get the rear element of the queue
int rear(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty\n");
        return -1;
    } else {
        return queue->items[queue->rear];
    }
}

int main() {
    struct Queue queue;
    initializeQueue(&queue);

    enqueue(&queue, 10);
    enqueue(&queue, 20);
    enqueue(&queue, 30);

    printf("Front element: %d\n", front(&queue)); // Output: 10
    printf("Rear element: %d\n", rear(&queue)); // Output: 30

    printf("Elements dequeued from queue: %d, %d\n", dequeue(&queue), dequeue(&queue)); // Output: 10, 20

    printf("Front element after dequeuing: %d\n", front(&queue)); // Output: 30

    return 0;
}
```

## Trees and Graphs

Trees and graphs are fundamental data structures in computer science that organize data hierarchically (trees) or non-hierarchically (graphs). Here’s an overview of each:

### Trees

> **Definition**: A tree is a hierarchical data structure consisting of nodes (vertices) connected by edges. It starts with a root node and each node has zero or more child nodes, forming a parent-child relationship.

**Key Concepts**:

- **Root**: The topmost node in a tree.
- **Parent**: A node from which another node (child) is directly descended.
- **Child**: A node directly connected to another node (parent) via an edge.
- **Leaf**: A node with no children.
- **Subtree**: A tree structure within a tree, starting from any node.
- **Depth**: The level of a node in the tree from the root (root has depth 0).
- **Height**: The maximum depth of any node in the tree.

**Types of Trees**:

- **Binary Tree**: Each node has at most two children (left and right).
- **Binary Search Tree (BST)**: A binary tree where for each node, all nodes in the left subtree have values less than the node’s value, and all nodes in the right subtree have values greater.
- **AVL Tree**: A self-balancing BST where the difference in heights of left and right subtrees of any node is at most 1.
- **B-tree**: A self-balancing tree data structure that maintains sorted data and allows searches, sequential access, insertions, and deletions in logarithmic time.

**Applications**:

- Hierarchical data representation (file systems, organization charts).
- Searching, sorting, and indexing algorithms (BSTs).
- Database management systems (B-trees).

### Graphs

> **Definition**: A graph is a non-linear data structure consisting of vertices (nodes) connected by edges. It models pairwise relationships between objects.

**Key Concepts**:

- **Vertices (Nodes)**: Represent entities or objects.
- **Edges**: Connections between nodes representing relationships.
- **Directed Graph**: Graph where edges have a direction (from one vertex to another).
- **Undirected Graph**: Graph where edges have no direction.
- **Weighted Graph**: Graph where edges have weights/costs.
- **Cyclic Graph**: Graph containing at least one cycle (a path that starts and ends at the same vertex).
- **Acyclic Graph (DAG - Directed Acyclic Graph)**: Graph with no cycles.

**Types of Graphs**:

- **Tree**: A connected acyclic graph with N nodes and N-1 edges.
- **Complete Graph**: A graph where each pair of distinct vertices is connected by a unique edge.
- **Bipartite Graph**: A graph whose vertices can be divided into two disjoint sets such that no two graph vertices within the same set are adjacent.

**Applications**:

- Social networks (friendship graphs).
- Route finding and shortest path algorithms (Dijkstra's algorithm, Floyd-Warshall algorithm).
- Dependency resolution (software packages).

# File Handling in C

1. **File Pointer (`FILE`)**:

   - In C, file operations are performed using a `FILE` pointer.
   - `FILE` is a structure defined in `<stdio.h>`.

2. **Opening a File**:

   - To open a file, use `fopen()` function.
   - Syntax: `FILE *fptr = fopen(const char *filename, const char *mode);`
   - Modes: `"r"` (read), `"w"` (write), `"a"` (append), `"r+"` (read/write), `"w+"` (read/write, truncates file), `"a+"` (read/append).

3. **Closing a File**:

   - Always close a file using `fclose()` after operations.
   - Syntax: `int fclose(FILE *fptr);`

4. **Reading from a File**:

   - Use `fscanf()` or `fgets()` to read from a file.
   - Example: `fscanf(fptr, "%s", buffer);`

5. **Writing to a File**:

   - Use `fprintf()` or `fputs()` to write to a file.
   - Example: `fprintf(fptr, "Hello, World!");`

6. **End-of-File (EOF)**:

   - `EOF` is a constant defined in `<stdio.h>` indicating end-of-file condition.
   - Use it to check end of file in loops: `while (fscanf(fptr, "%s", buffer) != EOF) { ... }`

7. **Error Handling**:
   - Check for file open errors using `if (fptr == NULL) { ... }`

# Programs

**24. Question** Display Contents of a File

```c
#include <stdio.h>

int main() {
    FILE *fptr;
    char filename[100], ch;

    printf("Enter the filename to open for reading: ");
    scanf("%s", filename);

    // Open file
    fptr = fopen(filename, "r");
    if (fptr == NULL) {
        printf("Error opening file %s\n", filename);
        return 1;
    }

    // Read contents character by character and display
    while ((ch = fgetc(fptr)) != EOF) {
        putchar(ch); // Print character to standard output
    }

    // Close file
    fclose(fptr);

    return 0;
}
```

- This program opens a file specified by the user and displays its contents character by character using `fgetc()`.

**25. Question** Copy File with Lowercase to Uppercase

```c
#include <stdio.h>
#include <ctype.h> // For toupper()

int main() {
    FILE *source, *target;
    char source_filename[100], target_filename[100], ch;

    printf("Enter source filename: ");
    scanf("%s", source_filename);

    printf("Enter target filename: ");
    scanf("%s", target_filename);

    // Open source file for reading
    source = fopen(source_filename, "r");
    if (source == NULL) {
        printf("Error opening source file %s\n", source_filename);
        return 1;
    }

    // Open target file for writing
    target = fopen(target_filename, "w");
    if (target == NULL) {
        printf("Error opening target file %s\n", target_filename);
        fclose(source);
        return 1;
    }

    // Copy contents, converting lowercase to uppercase
    while ((ch = fgetc(source)) != EOF) {
        if (islower(ch)) {
            ch = toupper(ch); // Convert lowercase to uppercase
        }
        fputc(ch, target); // Write character to target file
    }

    // Close files
    fclose(source);
    fclose(target);

    printf("File copied successfully.\n");

    return 0;
}
```

- It copies one file to another while converting all lowercase characters to uppercase using `fgetc()` and `fputc()`.
  **26. Question** Count Occurrences of a Character in a File

```c
#include <stdio.h>

int main(int argc, char *argv[]) {
    FILE *fptr;
    char filename[100], ch;
    char search_char;
    int count = 0;

    if (argc != 3) {
        printf("Usage: %s <filename> <character>\n", argv[0]);
        return 1;
    }

    // Retrieve filename and search character from command line arguments
    strcpy(filename, argv[1]);
    search_char = argv[2][0];

    // Open file
    fptr = fopen(filename, "r");
    if (fptr == NULL) {
        printf("Error opening file %s\n", filename);
        return 1;
    }

    // Count occurrences of search_char
    while ((ch = fgetc(fptr)) != EOF) {
        if (ch == search_char) {
            count++;
        }
    }

    // Close file
    fclose(fptr);

    // Display count
    printf("Character '%c' occurs %d times in file %s.\n", search_char, count, filename);

    return 0;
}
```

- The program counts occurrences of a specified character in a text file provided as command line arguments.

**27. Question** Modify Value in Binary File

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX_VALUES 10

int main(int argc, char *argv[]) {
    FILE *fptr;
    int values[MAX_VALUES];
    char filename[100];
    int index, new_value;

    if (argc != 12) { // Program name + 10 integers + filename
        printf("Usage: %s <filename> <val1> <val2> ... <val10> <index> <new_value>\n", argv[0]);
        return 1;
    }

    // Retrieve filename and values from command line arguments
    strcpy(filename, argv[1]);
    for (int i = 0; i < MAX_VALUES; i++) {
        values[i] = atoi(argv[2 + i]); // Convert string to integer
    }
    index = atoi(argv[12]);
    new_value = atoi(argv[13]);

    // Open file for writing
    fptr = fopen(filename, "wb");
    if (fptr == NULL) {
        printf("Error opening file %s\n", filename);
        return 1;
    }

    // Write values to file
    fwrite(values, sizeof(int), MAX_VALUES, fptr);

    // Close file
    fclose(fptr);

    // Modify value at index
    values[index] = new_value;

    // Display modified values
    printf("Modified values:\n");
    for (int i = 0; i < MAX_VALUES; i++) {
        printf("%d ", values[i]);
    }
    printf("\n");

    return 0;
}
```

- It creates a binary file, writes 10 integers into it, allows the user to modify a value at a specific index, and prints all values.

**28. Question**. Merge Two Files into Third File

```c
#include <stdio.h>

int main(int argc, char *argv[]) {
    FILE *fptr1, *fptr2, *fptr3;
    char filename1[100], filename2[100], filename3[100];
    char ch;

    if (argc != 4) {
        printf("Usage: %s <filename1> <filename2> <filename3>\n", argv[0]);
        return 1;
    }

    // Retrieve filenames from command line arguments
    strcpy(filename1, argv[1]);
    strcpy(filename2, argv[2]);
    strcpy(filename3, argv[3]);

    // Open first file for reading
    fptr1 = fopen(filename1, "r");
    if (fptr1 == NULL) {
        printf("Error opening file %s\n", filename1);
        return 1;
    }

    // Open second file for reading
    fptr2 = fopen(filename2, "r");
    if (fptr2 == NULL) {
        printf("Error opening file %s\n", filename2);
        fclose(fptr1);
        return 1;
    }

    // Open third file for writing
    fptr3 = fopen(filename3, "w");
    if (fptr3 == NULL) {
        printf("Error opening file %s\n", filename3);
        fclose(fptr1);
        fclose(fptr2);
        return 1;
    }

    // Copy contents of first file to third file
    while ((ch = fgetc(fptr1)) != EOF) {
        fputc(ch, fptr3);
    }

    // Copy contents of second file to third file
    while ((ch = fgetc(fptr2)) != EOF) {
        fputc(ch, fptr3);
    }

    // Close files
    fclose(fptr1);
    fclose(fptr2);
    fclose(fptr3);

    printf("Files %s and %s merged into %s\n", filename1, filename2, filename3);

    return 0;
}
```

- This program merges contents of two files into a third file by sequentially reading from the first two files and writing to the third file using `fgetc()` and `fputc()`.

# Searching and Sorting

## Searching

> **Definition**: Searching is the process of finding a particular element (or determining its absence) in a collection of elements.

**Functions**:

- **Linear Search**: Sequentially checks each element of a list until a match is found or the whole list has been searched.
- **Binary Search**: Efficiently locates a target value within a sorted array by repeatedly dividing the search interval in half.

**Types**:

- **Linear Search**:

  - **Unordered Linear Search**: Used for unsorted arrays/lists.
  - **Ordered Linear Search**: Used for sorted arrays/lists for early termination upon finding the element.

- **Binary Search**:
  - **Iterative Binary Search**: Uses a loop to divide the search interval iteratively.
  - **Recursive Binary Search**: Uses recursion to divide the search interval recursively.

## Sorting

> **Definition**: Sorting refers to arranging elements of a list in a specific order, such as numerical or lexicographical order.

**Functions**:

- **Bubble Sort**: Repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order.
- **Selection Sort**: Divides the list into a sorted and an unsorted region, repeatedly selects the smallest (or largest) element from the unsorted region and swaps it with the leftmost unsorted element.
- **Insertion Sort**: Builds the final sorted array/list one item at a time by inserting each item into its correct position.
- **Merge Sort**: Divides the list into smaller sublists, recursively sorts each sublist, and then merges the sorted sublists back together to form the final sorted list.
- **Quick Sort**: Selects a pivot element and partitions the list into two sublists around the pivot, recursively sorts each sublist, and combines them to form the final sorted list.

**Types**:

- **Simple Sorting Algorithms**:

  - **Bubble Sort**: Simple but inefficient for large lists.
  - **Selection Sort**: Simple and intuitive for small lists.
  - **Insertion Sort**: Efficient for small or nearly sorted lists.

- **Advanced Sorting Algorithms**:
  - **Merge Sort**: Efficient for large lists due to its divide-and-conquer approach.
  - **Quick Sort**: Efficient for large lists and widely used due to its average-case time complexity.

# Programs

**29. Question**. Linear Search

```c
#include <stdio.h>

// Function to perform linear search
int linearSearch(int arr[], int n, int key) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == key) {
            return i; // Return index of key if found
        }
    }
    return -1; // Return -1 if key not found
}

int main() {
    int arr[] = { 10, 20, 30, 40, 50 };
    int n = sizeof(arr) / sizeof(arr[0]);
    int key = 30;

    int result = linearSearch(arr, n, key);

    if (result != -1) {
        printf("Element found at index %d.\n", result);
    } else {
        printf("Element not found.\n");
    }

    return 0;
}
```

**30. Question** Binary Search

```c
#include <stdio.h>

// Function to perform iterative binary search
int binarySearch(int arr[], int left, int right, int key) {
    while (left <= right) {
        int mid = left + (right - left) / 2;

        if (arr[mid] == key) {
            return mid; // Return index of key if found
        } else if (arr[mid] < key) {
            left = mid + 1; // Search in the right half
        } else {
            right = mid - 1; // Search in the left half
        }
    }

    return -1; // Return -1 if key not found
}

int main() {
    int arr[] = { 10, 20, 30, 40, 50 };
    int n = sizeof(arr) / sizeof(arr[0]);
    int key = 30;

    int result = binarySearch(arr, 0, n - 1, key);

    if (result != -1) {
        printf("Element found at index %d.\n", result);
    } else {
        printf("Element not found.\n");
    }

    return 0;
}
```

**31. Question** Bubble Sort

```c
#include <stdio.h>

// Function to perform bubble sort
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Swap arr[j] and arr[j + 1]
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

int main() {
    int arr[] = { 64, 34, 25, 12, 22, 11, 90 };
    int n = sizeof(arr) / sizeof(arr[0]);

    bubbleSort(arr, n);

    printf("Sorted array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}
```

**32. Question** Selection Sort

```c
#include <stdio.h>

// Function to perform selection sort
void selectionSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int min_idx = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[min_idx]) {
                min_idx = j;
            }
        }
        // Swap arr[i] and arr[min_idx]
        int temp = arr[i];
        arr[i] = arr[min_idx];
        arr[min_idx] = temp;
    }
}

int main() {
    int arr[] = { 64, 25, 12, 22, 11 };
    int n = sizeof(arr) / sizeof(arr[0]);

    selectionSort(arr, n);

    printf("Sorted array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}
```

**33. Question** Insertion Sort

```c
#include <stdio.h>

// Function to perform insertion sort
void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;

        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}

int main() {
    int arr[] = { 12, 11, 13, 5, 6 };
    int n = sizeof(arr) / sizeof(arr[0]);

    insertionSort(arr, n);

    printf("Sorted array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}
```

**34. Question** Merge Sort

```c
#include <stdio.h>

// Merge function for merge sort
void merge(int arr[], int left, int mid, int right) {
    int n1 = mid - left + 1;
    int n2 = right - mid;
    int L[n1], R[n2];

    // Copy data to temp arrays L[] and R[]
    for (int i = 0; i < n1; i++)
        L[i] = arr[left + i];
    for (int j = 0; j < n2; j++)
        R[j] = arr[mid + 1 + j];

    // Merge the temp arrays back into arr[left..right]
    int i = 0; // Initial index of first subarray
    int j = 0; // Initial index of second subarray
    int k = left; // Initial index of merged subarray

    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) {
            arr[k] = L[i];
            i++;
        } else {
            arr[k] = R[j];
            j++;
        }
        k++;
    }

    // Copy the remaining elements of L[], if any
    while (i < n1) {
        arr[k] = L[i];
        i++;
        k++;
    }

    // Copy the remaining elements of R[], if any
    while (j < n2) {
        arr[k] = R[j];
        j++;
        k++;
    }
}

// Recursive function for merge sort
void mergeSort(int arr[], int left, int right) {
    if (left < right) {
        int mid = left + (right - left) / 2;

        // Sort first and second halves
        mergeSort(arr, left, mid);
        mergeSort(arr, mid + 1, right);

        // Merge the sorted halves
        merge(arr, left, mid, right);
    }
}

int main() {
    int arr[] = { 12, 11, 13, 5, 6, 7 };
    int n = sizeof(arr) / sizeof(arr[0]);

    mergeSort(arr, 0, n - 1);

    printf("Sorted array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}
```

- **Linear Search**: Searches for an element by sequentially checking each element in the array until the target element is found or all elements are checked.
- **Binary Search**: Efficiently searches a sorted array by repeatedly dividing the search interval in half.
- **Bubble Sort**: Simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order.
- **Selection Sort**: Sorts an array by repeatedly finding the minimum element from the unsorted part and putting it at the beginning.
- **Insertion Sort**: Builds the final sorted array one item at a time by inserting each item into its correct position.
- **Merge Sort**: Efficient sorting algorithm that divides the array into halves, recursively sorts each half, and merges them back in sorted order.

# Time Complexity

> **Time Complexity** measures the amount of time an algorithm takes to run as a function of the size of the input data. It gives an idea of how the algorithm scales with input size.

# Space Complexity

> **Space Complexity** measures the amount of memory space an algorithm requires as a function of the size of the input data. It includes both auxiliary space (extra space) and space used by the input itself.

## Table of Time and Space Complexities

| Algorithm      | Best Time Complexity | Average Time Complexity | Worst Time Complexity | Worst Space Complexity | Stability |
| -------------- | -------------------- | ----------------------- | --------------------- | ---------------------- | --------- |
| **Searching**  |                      |                         |                       |                        |           |
| Linear Search  | O(1)                 | O(n)                    | O(n)                  | O(1)                   | Stable    |
| Binary Search  | O(1)                 | O(log n)                | O(log n)              | O(1)                   | Stable    |
|                |                      |                         |                       |                        |           |
| **Sorting**    |                      |                         |                       |                        |           |
| Bubble Sort    | O(n)                 | O(n^2)                  | O(n^2)                | O(1)                   | Stable    |
| Selection Sort | O(n^2)               | O(n^2)                  | O(n^2)                | O(1)                   | Unstable  |
| Insertion Sort | O(n)                 | O(n^2)                  | O(n^2)                | O(1)                   | Stable    |
| Merge Sort     | O(n log n)           | O(n log n)              | O(n log n)            | O(n)                   | Stable    |
| Quick Sort     | O(n log n)           | O(n log n)              | O(n^2)                | O(log n)               | Unstable  |

- **Best Time Complexity**: The minimum time required for the best-case scenario.
- **Average Time Complexity**: The average time across all possible inputs of size \( n \).
- **Worst Time Complexity**: The maximum time required for the worst-case scenario.
- **Worst Space Complexity**: The maximum space used by the algorithm.

- **Stable Sorting Algorithm**: Maintains the relative order of records with equal keys.
- **Unstable Sorting Algorithm**: Does not maintain the relative order of records with equal keys.

- **Linear Search**:

  - Time Complexity: O(1) to O(n)
  - Space Complexity: O(1)

- **Binary Search**:

  - Time Complexity: O(1) to O(log n)
  - Space Complexity: O(1)

- **Bubble Sort**:

  - Time Complexity: O(n) to O(n^2)
  - Space Complexity: O(1)

- **Selection Sort**:

  - Time Complexity: O(n^2)
  - Space Complexity: O(1)

- **Insertion Sort**:

  - Time Complexity: O(n) to O(n^2)
  - Space Complexity: O(1)

- **Merge Sort**:

  - Time Complexity: O(n log n)
  - Space Complexity: O(n)

- **Quick Sort**:
  - Time Complexity: O(n log n) to O(n^2)
  - Space Complexity: O(log n)
