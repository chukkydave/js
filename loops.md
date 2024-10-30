
JavaScript Loops Overview

Loops in JavaScript allow us to repeat a block of code a specified number of times or until a condition is met. Understanding loops is essential for automating repetitive tasks, processing data structures, and improving code efficiency.

Types of Loops in JavaScript:

	1.	for loop
	2.	while loop
	3.	do...while loop
	4.	for...of loop
	5.	for...in loop

1. for Loop

The for loop is one of the most commonly used loops. It repeats code a specific number of times and is especially useful when the number of iterations is known.

Syntax:

for (initialization; condition; increment/decrement) {
    // Code to execute in each iteration
}

Explanation of Components:

	•	Initialization: Sets up a variable before the loop starts, commonly used as a counter.
	•	Condition: Determines if the loop should continue running. The loop stops when this condition is false.
	•	Increment/Decrement: Updates the counter after each iteration.

Example 1: Basic for Loop

for (let i = 0; i < 5; i++) {
    console.log(i);
}
// Output: 0, 1, 2, 3, 4

Use Case:

	•	Counting down days until an event or looping through a list of numbers to perform calculations.

Advanced Example: Nested for Loop

for (let i = 1; i <= 3; i++) {
    for (let j = 1; j <= 3; j++) {
        console.log(`i: ${i}, j: ${j}`);
    }
}
// Demonstrates the concept of nested loops.

2. while Loop

The while loop continues to execute as long as a specified condition is true. It’s ideal when the number of iterations is unknown.

Syntax:

while (condition) {
    // Code to execute while the condition is true
}

Explanation of Keywords:

	•	Condition: The loop checks this condition before every iteration. If true, it runs; if false, it stops.

Example 1: Basic while Loop

let count = 0;
while (count < 5) {
    console.log(count);
    count++;
}
// Output: 0, 1, 2, 3, 4

Use Case:

	•	Continuously prompting for user input until valid data is provided.

Advanced Example: Simulating an ATM PIN Verification

let correctPIN = 1234;
let attempts = 3;
let userPIN;

while (attempts > 0) {
    userPIN = prompt("Enter your PIN:");
    if (parseInt(userPIN) === correctPIN) {
        console.log("Access granted");
        break;
    } else {
        attempts--;
        console.log(`Incorrect PIN. You have ${attempts} attempts left.`);
    }
}

3. do...while Loop

The do...while loop is similar to the while loop, except it executes the code block at least once before checking the condition. This is useful when you want to run code at least once regardless of the condition.

Syntax:

do {
    // Code to execute
} while (condition);

Example 1: Basic do...while Loop

let i = 0;
do {
    console.log(i);
    i++;
} while (i < 5);
// Output: 0, 1, 2, 3, 4

Use Case:

	•	Prompting a user at least once for a specific action, such as accepting terms and conditions.

Advanced Example: Basic User Validation with do...while

let input;
do {
    input = prompt("Enter a number greater than 10:");
} while (parseInt(input) <= 10);
console.log("Thank you for following instructions!");

4. for...of Loop

The for...of loop is used to iterate over iterable objects like arrays, strings, maps, and sets. It’s ideal for directly working with values rather than counters.

Syntax:

for (variable of iterable) {
    // Code to execute for each value in the iterable
}

Explanation of Keywords:

	•	variable: Stores the current value in each iteration.
	•	iterable: An object that can be iterated over, such as an array or a string.

Example 1: Looping through an Array

const colors = ["red", "green", "blue"];
for (let color of colors) {
    console.log(color);
}
// Output: "red", "green", "blue"

Use Case:

	•	Processing items in an array like showing each item in a product list.

Advanced Example: Summing Numbers in an Array

const numbers = [1, 2, 3, 4];
let sum = 0;
for (let number of numbers) {
    sum += number;
}
console.log(sum); // 10

5. for...in Loop

The for...in loop iterates over the properties of an object, useful for accessing keys in an object.

Syntax:

for (variable in object) {
    // Code to execute for each key in the object
}

Explanation:

	•	variable: Stores each key or property name during iteration.
	•	object: The object from which keys are iterated over.

Example 1: Looping through Object Properties

const person = { name: "Alice", age: 25, city: "Paris" };
for (let key in person) {
    console.log(key + ": " + person[key]);
}
// Output: "name: Alice", "age: 25", "city: Paris"

Use Case:

	•	Extracting or manipulating object data.

Advanced Example: Filtering Properties Based on Condition

const user = { name: "John", age: 30, active: true, premium: false };
let activeProperties = {};
for (let key in user) {
    if (user[key] === true) {
        activeProperties[key] = user[key];
    }
}
console.log(activeProperties); // { active: true }

Other Loop Keywords: break and continue

	1.	break: Exits the loop entirely, skipping all remaining iterations.
	•	Useful for stopping a loop when a certain condition is met.

for (let i = 0; i < 10; i++) {
    if (i === 5) break;
    console.log(i); // Output: 0, 1, 2, 3, 4
}


	2.	continue: Skips the current iteration and moves to the next one.
	•	Useful for skipping specific cases in a loop.

for (let i = 0; i < 5; i++) {
    if (i === 2) continue;
    console.log(i); // Output: 0, 1, 3, 4
}



Summary

	•	for Loop: Ideal for a fixed number of repetitions.
	•	while Loop: Used when the number of repetitions is unknown.
	•	do...while Loop: Executes at least once, regardless of the condition.
	•	for...of Loop: Best for iterating over arrays and other iterables.
	•	for...in Loop: Designed for iterating over object properties.

This guide should give a solid foundation in JavaScript loops and help in understanding the practical applications of each type. Let me know if you’d like further details on any section!
