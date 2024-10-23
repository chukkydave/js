

1. TypeOf Operator

Explanation:

The typeof operator is used to check the data type of a variable or value in JavaScript. It returns a string indicating the type of the value.

Syntax:

typeof operand;

Common Types:

	•	number: for numbers.
	•	string: for strings.
	•	boolean: for true/false.
	•	object: for objects (including null).
	•	function: for functions.
	•	undefined: for undefined variables.

Example:

let x = 10;
console.log(typeof x);  // "number"

let name = "Alice";
console.log(typeof name);  // "string"

let isStudent = true;
console.log(typeof isStudent);  // "boolean"

let person = { name: "Alice", age: 25 };
console.log(typeof person);  // "object"

let func = function() {};
console.log(typeof func);  // "function"

Use Case:

Checking the type of user input to ensure proper validation.

Practice Question:

Write a function checkType that accepts a value and logs the type of the value using typeof.

2. Type Conversion

Explanation:

JavaScript allows converting values from one type to another. This is often useful when performing operations that expect certain data types.

Types of Conversion:

	1.	String Conversion: Converts values to strings.
	•	Using String() or .toString()
	2.	Number Conversion: Converts values to numbers.
	•	Using Number(), parseInt(), or parseFloat()
	3.	Boolean Conversion: Converts values to true or false.
	•	Using Boolean()

Examples:

String Conversion:

let num = 123;
let strNum = String(num);
console.log(strNum);  // "123"

Number Conversion:

let str = "456";
let num = Number(str);
console.log(num);  // 456

Boolean Conversion:

let emptyString = "";
let boolValue = Boolean(emptyString);
console.log(boolValue);  // false

Use Case:

Converting form input values (which are usually strings) to the required type for calculations.

Practice Question:

Write a function convertToNumber that takes a string input and converts it to a number. If the conversion fails, return NaN.

3. Errors (Try, Catch, Finally & Throw Statements)

Explanation:

JavaScript uses try...catch to handle errors that may occur during code execution, without stopping the program.

	•	try: Defines a block of code to test for errors.
	•	catch: Defines a block of code to handle any error.
	•	finally: Executes after try and catch, regardless of the outcome.
	•	throw: Allows manually throwing an error.

Syntax:

try {
    // Code that may cause an error
} catch (error) {
    // Code to handle the error
} finally {
    // Code that always runs (optional)
}

Example:

try {
    let result = 5 / 0;
    if (!isFinite(result)) {
        throw new Error("Cannot divide by zero");
    }
} catch (error) {
    console.log("Error:", error.message);  // "Error: Cannot divide by zero"
} finally {
    console.log("This will run regardless of the error.");
}

Use Case:

Handling API call failures without crashing the application.

Practice Question:

Write a function safeDivide that accepts two numbers and returns their division. If the second number is zero, throw an error saying “Division by zero is not allowed”.

4. Strict Mode

Explanation:

"use strict"; enables strict mode in JavaScript, which helps catch common coding mistakes and makes JavaScript more secure by preventing the use of certain error-prone features.

Key Features:

	•	Disallows the use of undeclared variables.
	•	Prevents the use of duplicate parameter names.
	•	Disallows writing to read-only properties.

Syntax:

"use strict";

Example:

"use strict";
let x = 10;
y = 20;  // Error: y is not defined

Use Case:

Preventing the accidental creation of global variables.

Practice Question:

Create a function in strict mode and try assigning a value to an undeclared variable. Catch and log the error.

5. Reserved Words

Explanation:

Reserved words are words that cannot be used as identifiers (like variable names or function names) in JavaScript because they have special meanings.

Common Reserved Words:

	•	abstract, boolean, break, case, catch, class, const, continue, debugger, default, delete, do, else, enum, export, extends, false, finally, for, function, if, import, in, instanceof, interface, let, null, return, super, switch, this, throw, true, try, typeof, var, void, while, with

Example:

// Incorrect
let if = 10;  // Error: 'if' is a reserved word

// Correct
let condition = 10;

Use Case:

Avoiding errors by choosing valid variable names.

Practice Question:

List 5 reserved words in JavaScript and explain why they cannot be used as variable names.

Summary of Practice Test:

	1.	TypeOf: Create a function identifyType that takes multiple inputs and returns the type of each one.
	2.	Type Conversion: Write a program that converts a variety of user inputs (string, boolean, etc.) to different types (e.g., number, boolean) and logs the results.
	3.	Errors: Implement a safeCalculate function that performs division, but gracefully handles division by zero using try…catch.
	4.	Strict Mode: Enable strict mode in a function and demonstrate an error by trying to assign a value to an undeclared variable.
	5.	Reserved Words: Have students attempt to use reserved words as variable names and discuss the resulting errors.
