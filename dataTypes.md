

1. Data Types

JavaScript has several fundamental data types, which are essential for storing different kinds of information. Here, we’ll cover Numbers, Strings, Booleans, Undefined, Null, Arrays, and Objects, along with their associated methods.

1.1. Numbers

Numbers in JavaScript can be integers or floating-point values.

Examples:

let age = 25;        // Integer
let price = 99.99;   // Floating-point number

Methods:

	•	toFixed(): Formats a number to a fixed number of decimal places.
	•	toString(): Converts a number to a string.
	•	Math: A built-in object with methods like Math.round(), Math.random(), Math.floor().

Example:

let num = 5.6789;
console.log(num.toFixed(2));  // Output: 5.68
console.log(Math.floor(num)); // Output: 5

Use Case:

	•	Calculating prices in e-commerce websites.

Edge Case:

	•	Dealing with floating-point precision issues:

console.log(0.1 + 0.2); // Output: 0.30000000000000004



Classwork:

	1.	Write a function that rounds a number to two decimal places.
	2.	Generate a random integer between 1 and 10 using Math.random() and Math.floor().

1.2. Strings

Strings represent sequences of characters.

Examples:

let message = "Hello, World!";
let name = 'Alice';

Methods:

	•	length: Returns the length of a string.
	•	toUpperCase(): Converts the string to uppercase.
	•	toLowerCase(): Converts the string to lowercase.
	•	includes(): Checks if a string contains another string.
	•	slice(): Extracts a section of a string.

Example:

let greeting = "Good morning!";
console.log(greeting.toUpperCase()); // Output: GOOD MORNING!
console.log(greeting.includes("morning")); // Output: true

Use Case:

	•	Validating email addresses or user inputs in forms.

Edge Case:

	•	Empty strings:

let emptyString = "";
console.log(emptyString.length); // Output: 0



Classwork:

	1.	Write a function that takes a string and returns it in reverse order.
	2.	Check if a string contains a specific substring using includes().

1.3. Booleans

Booleans represent logical values: true or false.

Examples:

let isLoggedIn = true;
let isMember = false;

Use Case:

	•	Toggling UI elements based on a user’s login status.

Edge Case:

	•	Type coercion with booleans:

console.log(Boolean(0));     // Output: false
console.log(Boolean(""));    // Output: false
console.log(Boolean(" "));   // Output: true (space is a truthy value)



Classwork:

	1.	Write a function that returns true if a number is positive, otherwise false.
	2.	Use booleans to control the visibility of a section on a webpage (use an if condition).

1.4. Undefined and Null

	•	Undefined: A variable that has been declared but not assigned a value.
	•	Null: Represents the intentional absence of any object value.

Examples:

let user;
let selectedItem = null;
console.log(user);        // Output: undefined
console.log(selectedItem); // Output: null

Use Case:

	•	undefined can signal that a variable is uninitialized.
