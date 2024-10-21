##Arrow Functions
1. Arrow Functions

Arrow functions are a more concise way to write function expressions in JavaScript. They do not have their own this binding, making them useful in certain contexts like callbacks and array methods.

Syntax:

const functionName = (parameter1, parameter2) => {
  // function body
  return expression;
};

If the function has a single expression, the return keyword and curly braces {} can be omitted:

const add = (a, b) => a + b;

Key Characteristics:

	•	Shorter syntax than regular functions.
	•	this value is lexically bound, meaning it inherits from the parent scope.
	•	Cannot be used as constructors.

Example:

const multiply = (a, b) => a * b;
console.log(multiply(5, 3)); // Output: 15

Classwork:

	1.	Convert the following function to an arrow function:

function greet(name) {
  return `Hello, ${name}`;
}


	2.	Write an arrow function that takes an array of numbers and returns a new array with all numbers doubled.

2. Arrays

An array is a collection of elements that are stored in a single variable. Arrays can hold multiple values and provide many methods to manipulate data.

Declaration:

let fruits = ['Apple', 'Banana', 'Mango'];

Common Array Methods:

	•	.push(): Adds an item to the end of an array.
	•	.pop(): Removes the last item.
	•	.shift(): Removes the first item.
	•	.unshift(): Adds an item to the beginning.
	•	.map(): Creates a new array by applying a function to each element.
	•	.filter(): Creates a new array with elements that pass a test.

Example:

let numbers = [1, 2, 3, 4, 5];
let doubled = numbers.map(n => n * 2);
console.log(doubled); // Output: [2, 4, 6, 8, 10]

Classwork:

	1.	Create an array of numbers from 1 to 10. Write a function to filter out numbers greater than 5.
	2.	Write a function to return the sum of all numbers in an array.

3. Objects

Objects are collections of key-value pairs. They are used to store related data and more complex structures.

Declaration:

let person = {
  name: 'John',
  age: 30,
  occupation: 'Developer'
};

Accessing Properties:

	•	Dot notation: person.name
	•	Bracket notation: person['age']

Adding/Modifying Properties:

person.country = 'USA';
person.age = 31;

Example:

let car = {
  brand: 'Toyota',
  model: 'Corolla',
  year: 2020,
  start: function() {
    console.log(`${this.brand} ${this.model} is starting`);
  }
};
car.start(); // Output: "Toyota Corolla is starting"

Classwork:

	1.	Create an object to represent a book with properties like title, author, and pages.
	2.	Write a function that takes an object and prints all its property names and values.

4. Other Data Types

	•	Strings: A sequence of characters.

let message = 'Hello, world!';
console.log(message.length); // 13
console.log(message.toUpperCase()); // 'HELLO, WORLD!'


	•	Numbers: Represents numeric values.

let price = 100.5;
let discount = 10;
console.log(price - discount); // 90.5


	•	Booleans: Represents logical values true or false.

let isAvailable = true;
console.log(isAvailable); // true


	•	Null and Undefined: null is an intentional absence of value, while undefined is a default value for uninitialized variables.

Example:

let unknown;
console.log(unknown); // Output: undefined
unknown = null;
console.log(unknown); // Output: null

Classwork:

	1.	Create a string variable and write functions to return the string in uppercase, lowercase, and its length.
	2.	Create a boolean variable and use it in a conditional statement that prints a message based on its value.

5. Related Topics: Destructuring and Spread Operator

Destructuring allows you to extract values from arrays or properties from objects into distinct variables.

Array Destructuring:

let [first, second] = ['Apple', 'Banana'];
console.log(first); // Apple

Object Destructuring:

let {name, age} = {name: 'John', age: 30};
console.log(name); // John

Spread Operator:

The spread operator ... is used to expand arrays or objects.

Example:

let arr1 = [1, 2, 3];
let arr2 = [...arr1, 4, 5];
console.log(arr2); // [1, 2, 3, 4, 5]

Classwork:

	1.	Use destructuring to extract the first two elements of an array.
	2.	Use the spread operator to combine two arrays into one.

6. Practice Exercises

	1.	Arrow Functions: Write an arrow function that takes an array of numbers and returns an array of squared numbers.
	2.	Arrays: Create an array of names. Write a function to return names that start with the letter ‘A’.
	3.	Objects: Create an object representing a mobile phone, with properties like brand, model, and price. Write a function to print all properties of the phone.
	4.	Destructuring: Use destructuring to assign variables from an object representing a student, including their name, age, and grade.
	5.	Spread Operator: Write a function that merges two arrays of numbers and returns the result.

These notes should provide a comprehensive foundation for teaching JavaScript to your trainees. The examples and classwork exercises are designed to reinforce understanding and practical application.
