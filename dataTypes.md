

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

 Here are detailed lesson notes on Data Types (Arrays and Objects with their Methods), Operators, Control Structures, and Functions (Basics) with beginner and advanced explanations, examples, edge cases, and classwork.

1. Data Types: Arrays

Introduction:

An Array is a special type of object in JavaScript that allows you to store multiple values in a single variable. Arrays are zero-indexed, meaning the first element is at index 0.

Example:

let fruits = ['apple', 'banana', 'orange'];
console.log(fruits[0]); // Output: "apple"

Common Array Methods:

	1.	push(): Adds an element to the end of an array.

fruits.push('grape');
console.log(fruits); // Output: ['apple', 'banana', 'orange', 'grape']


	2.	pop(): Removes the last element from an array.

let removedFruit = fruits.pop();
console.log(removedFruit); // Output: 'grape'
console.log(fruits);       // Output: ['apple', 'banana', 'orange']


	3.	shift(): Removes the first element from an array.

let firstFruit = fruits.shift();
console.log(firstFruit); // Output: 'apple'
console.log(fruits);     // Output: ['banana', 'orange']


	4.	unshift(): Adds an element to the beginning of an array.

fruits.unshift('kiwi');
console.log(fruits); // Output: ['kiwi', 'banana', 'orange']


	5.	map(): Creates a new array by applying a function to each element of the original array.

let numbers = [1, 2, 3, 4];
let doubled = numbers.map(num => num * 2);
console.log(doubled); // Output: [2, 4, 6, 8]


	6.	filter(): Creates a new array with elements that pass a certain condition.

let evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]


	7.	reduce(): Applies a function to accumulate array values into a single value.

let sum = numbers.reduce((total, num) => total + num, 0);
console.log(sum); // Output: 10



Advanced Example:

Using the spread operator to clone and merge arrays:

let arr1 = [1, 2, 3];
let arr2 = [...arr1, 4, 5];
console.log(arr2); // Output: [1, 2, 3, 4, 5]

Edge Case:

	•	Accessing out-of-bounds elements:

console.log(fruits[10]); // Output: undefined



Classwork:

	1.	Create an array of numbers and write a function that returns a new array with each number squared.
	2.	Use filter() to return an array of all numbers greater than 10.

2. Data Types: Objects

Introduction:

An Object is a collection of key-value pairs, where each key is associated with a value. Objects allow for more complex data structures and are commonly used to store data about entities (e.g., a user or product).

Example:

let person = {
  name: 'John',
  age: 30,
  job: 'Engineer'
};
console.log(person.name); // Output: 'John'

Common Object Methods:

	1.	Object.keys(): Returns an array of the object’s keys.

console.log(Object.keys(person)); // Output: ['name', 'age', 'job']


	2.	Object.values(): Returns an array of the object’s values.

console.log(Object.values(person)); // Output: ['John', 30, 'Engineer']


	3.	Object.entries(): Returns an array of key-value pairs from an object.

console.log(Object.entries(person)); // Output: [['name', 'John'], ['age', 30], ['job', 'Engineer']]


	4.	Adding, modifying, and deleting properties:

person.city = 'New York';  // Add new property
person.age = 31;           // Modify existing property
delete person.job;         // Remove property
console.log(person);
// Output: {name: 'John', age: 31, city: 'New York'}


	5.	Object Destructuring:

const { name, age } = person;
console.log(name); // Output: 'John'



Advanced Example:

Nested objects:

let company = {
  name: 'Tech Corp',
  address: {
    city: 'San Francisco',
    state: 'CA'
  },
  employees: ['John', 'Jane', 'Mike']
};
console.log(company.address.city); // Output: 'San Francisco'
console.log(company.employees[1]); // Output: 'Jane'

Edge Case:

Accessing non-existent properties:

console.log(person.address); // Output: undefined

Classwork:

	1.	Create an object representing a car with properties make, model, and year. Add a method to print the car details.
	2.	Write a function that takes an object and returns the sum of all numeric values in the object.

3. Operators

Introduction:

Operators in JavaScript are used to perform operations on variables and values. Common types of operators include arithmetic, comparison, logical, and assignment operators.

Arithmetic Operators:

Used for mathematical operations:

	•	+, -, *, /, %

Example:

let sum = 5 + 3;    // Output: 8
let product = 4 * 7; // Output: 28

Comparison Operators:

Used to compare values:

	•	==, ===, !=, !==, <, >, <=, >=

Example:

console.log(10 == '10');  // Output: true (loose equality)
console.log(10 === '10'); // Output: false (strict equality)

Logical Operators:

Used for combining boolean expressions:

	•	&& (AND), || (OR), ! (NOT)

Example:

let isAdult = true;
let hasID = false;
console.log(isAdult && hasID); // Output: false

Assignment Operators:

Used to assign values to variables:

	•	=, +=, -=, *=, /=

Example:

let x = 5;
x += 3; // Same as x = x + 3
console.log(x); // Output: 8

Classwork:

	1.	Write a function that takes two numbers and returns true if both are positive.
	2.	Write a function that checks if a number is between 1 and 100.

