### Links
- [idiomatic.js](https://github.com/rwaldron/idiomatic.js)

### Naming Convention: "***Camel Casing***"

## Introduction to Javascript ES6
- JavaScript Alerts
	- `Function("Message");`
	- `alert();`
		- The `alert()` method displays an alert box with a message and an OK button.
	- `prompt();`
		- The `prompt()` method returns the input value if the user clicks "OK", otherwise it returns `null`.
- Data Types
	- To check: `typeof();`
	- String
		- Message: `"Message"`
	- Numbers
		- Message: `143`
	- Boolean
		- Message: `true`
- Variable
	- JavaScript Variables can be declared in 4 ways:
		- Automatically
		- Using `var`
		- Using `let`
		- Using `const
- String
	- Concatenation
		- `alert(message + " there, " + name);`
	- String Length
		- `stringName.length` (Variable)
		- The **`length`** data property of a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) value contains the length of the string in UTF-16 code units.
- Slicing
	- `stringName.slice(x,y);`
- Casing
	- `stringName.toUpperCase();`
	- `stringName.toLowerCase();`
- Basic Arithmetic and Modulo operator 
	- Addition: `a = b + c`
	- Subtraction: `a = b - c`
	- Multiplication: `a = b * c`
	- Division: `a = b / c`
	- Reminder (Modulo): `a = b % c`
- Increment and Decrement Expressions
	- Increment by 1: `i++`
	- Decrement by 1: `i--`
	- Increment by `a`: `i += a`
		- `i -= a`
		- `i /= a`
		- `i *= a`
		- `i %= a`

[[Function (.js)]]

## Intermediate JavaScript
- Random numbers
	- `Math.random();` random number between 0 and 0.999999999
- Control Statements
	- if else conditions
		 `if (condition){`
		 `function();`
		 `} else {`
		 `function2();`
		 `}`
		- condition: `===` for same data type
			- `==`, `>`, `<=`, `&&`, `||`
	- Arrays
		- `var array = [0, 1, 2, 3, 4]`
		- for individual `array[2]`
		- array length: `array.length`
		- to check a value in array `array.includes(3);` (similar for for loop)
		- add value in array: `array.push(value);`
		- remove value in array: `array.pop();`
	- While Loops
		- `while (condition) {
		  }`
	- For Loop
		- `for (let index = 0; index < array.length; index++) {
		  `const element = array[index];
		  `}`


## [[Document Object Model (DOM)]]