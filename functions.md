JavaScript Functions: General Notes

1. What is a Function?

A function is a block of code designed to perform a particular task. Functions allow you to reuse code, make your code more organized, and handle complex operations in a modular way.

Functions in JavaScript are defined using the function keyword followed by:

	•	The name of the function (optional).
	•	A list of parameters enclosed in parentheses ( ).
	•	A block of code enclosed in curly braces { } that defines the function’s body.

2. Function Declaration

This is the most common way to declare a function in JavaScript.

Syntax:

function functionName(parameters) {
  // Code to be executed
  return value;
}

Example:

function greet(name) {
  return `Hello, ${name}!`;
}
console.log(greet('Alice')); // Output: Hello, Alice!

Key Characteristics:

	•	Can be called before or after the declaration in the code (hoisting).
	•	Can accept parameters and return a value.

3. Function Expression

A function expression allows you to define a function as part of a variable assignment.

Syntax:

const functionName = function(parameters) {
  // Code to be executed
  return value;
};

Example:

const add = function(a, b) {
  return a + b;
};
console.log(add(5, 3)); // Output: 8

Key Characteristics:

	•	Function expressions are not hoisted; they must be defined before they are called.
	•	Useful for anonymous functions (functions without a name).

4. Parameters and Arguments

Parameters are variables listed in the function declaration. Arguments are values passed to the function when it is called.

Example:

function multiply(a, b) {
  return a * b;
}
console.log(multiply(2, 3)); // Output: 6

You can also use default parameters to provide default values for parameters when no argument is passed.

Example:

function greet(name = 'Guest') {
  return `Hello, ${name}!`;
}
console.log(greet()); // Output: Hello, Guest!

5. Returning Values

A function can return a value using the return statement. Once return is encountered, the function stops executing.

Example:

function square(x) {
  return x * x;
}
let result = square(4);
console.log(result); // Output: 16

6. Function Hoisting

In JavaScript, function declarations are hoisted, meaning you can call the function before the actual function declaration in your code.

Example:

console.log(sayHello()); // Output: Hello!
function sayHello() {
  return 'Hello!';
}

However, function expressions are not hoisted:

console.log(sayHello()); // Error: sayHello is not defined
const sayHello = function() {
  return 'Hello!';
};

7. Anonymous Functions

Anonymous functions are functions without a name, often used in situations where a function is used as a callback.

Example:

setTimeout(function() {
  console.log('This is an anonymous function');
}, 1000);

8. Arrow Functions

Arrow functions provide a shorter syntax for writing functions, especially for anonymous functions. They are explained in detail in the previous notes.

Example:

const sum = (a, b) => a + b;
console.log(sum(5, 10)); // Output: 15

9. Higher-Order Functions

A higher-order function is a function that takes another function as an argument or returns a function as a result.

Example:

function doMath(operation, a, b) {
  return operation(a, b);
}
function add(a, b) {
  return a + b;
}
console.log(doMath(add, 5, 10)); // Output: 15

10. Recursion

A recursive function is a function that calls itself in its body to solve a problem by breaking it down into smaller sub-problems.

Example:

function factorial(n) {
  if (n === 0) {
    return 1;
  }
  return n * factorial(n - 1);
}
console.log(factorial(5)); // Output: 120

11. IIFE (Immediately Invoked Function Expression)

An IIFE is a function that runs immediately after being defined.

Example:

(function() {
  console.log('This is an IIFE');
})();

Practice Exercises

	1.	Function Declaration:
Write a function named areaOfCircle that takes the radius as a parameter and returns the area of a circle (use the formula πr²).
	2.	Function Expression:
Create a function expression that converts Celsius to Fahrenheit and store it in a variable named convertTemperature. Use the formula (Celsius * 9/5) + 32.
	3.	Default Parameters:
Write a function calculateDiscount(price, discount = 0.1) that calculates the final price after applying a default discount of 10%. Call the function with and without the discount argument.
	4.	Returning Values:
Write a function max that takes two numbers and returns the greater one. If both numbers are equal, return either of them.
	5.	Anonymous Function:
Use an anonymous function to sort the array [5, 3, 8, 1] in ascending order using the .sort() method.
	6.	Arrow Function:
Create an arrow function double that takes an array of numbers and returns a new array with each number doubled.
	7.	Higher-Order Function:
Write a higher-order function applyOperation that takes a function and two numbers, and returns the result of applying the function to the two numbers. Use this with addition and multiplication functions.
	8.	Recursive Function:
Write a recursive function sumRange that calculates the sum of all numbers from 1 to a given number n.
	9.	IIFE:
Create an IIFE that prints "Hello World" immediately.

These notes cover general functions, including examples and exercises, and will help your trainees grasp the fundamentals of JavaScript functions. You can expand or modify the exercises based on the trainee’s progress.
