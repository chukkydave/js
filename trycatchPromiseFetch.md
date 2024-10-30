
JavaScript Error Handling

JavaScript’s error-handling features help us catch and respond to unexpected issues during code execution. Using try, catch, throw, and finally blocks, you can gracefully manage errors, maintain program stability, and provide clear messaging.

1. try and catch

	•	try block: Place code that might throw an error here. JavaScript will monitor this block for exceptions.
	•	catch block: Executes if an error occurs within the try block, giving us a way to handle the error gracefully.

Example:

try {
    let x = 10;
    let y = x + z; // Error, z is undefined
} catch (error) {
    console.log("An error occurred:", error.message); 
}

In this example:

	•	try monitors the code for issues.
	•	When an error is detected (like z being undefined), the catch block captures it, allowing for a response.

2. throw

The throw statement lets you create custom error messages, useful for input validation, conditions, or other checks where specific errors are needed.

Example:

function divide(a, b) {
    if (b === 0) {
        throw new Error("Cannot divide by zero");
    }
    return a / b;
}

try {
    console.log(divide(4, 0));
} catch (error) {
    console.log(error.message); 
}

This example:

	•	Throws a custom error if b is zero.
	•	The catch block captures the thrown error, and we can handle it accordingly.

3. finally

The finally block executes regardless of an error occurring, allowing for cleanup operations.

Example:

try {
    let result = 10 / 2;
} catch (error) {
    console.log(error);
} finally {
    console.log("Execution completed"); 
}

Here:

	•	finally will execute after try and catch, regardless of whether an error occurred, making it suitable for cleanup tasks.

JavaScript Promises

A Promise represents the future result of an asynchronous operation. A Promise can be in one of three states:

	•	Pending: Initial state, neither fulfilled nor rejected.
	•	Fulfilled: Operation completed successfully.
	•	Rejected: Operation failed.

Basic Promise Structure

let promise = new Promise((resolve, reject) => {
    let success = true;
    if (success) resolve("Success!");
    else reject("Failed!");
});

promise.then(result => console.log(result)).catch(error => console.log(error));

	•	resolve: Calls when the Promise completes successfully.
	•	reject: Calls when the Promise fails.

Promise Chaining

Promises allow chaining to sequence operations in a cleaner way than nested callbacks.

Example:

promise
    .then(result => result + " again")
    .then(final => console.log(final))  // Logs "Success! again" if resolved
    .catch(error => console.log(error));

Use Cases for Promises

	•	Loading data from an API
	•	Handling timeouts or delays
	•	File uploads or downloads

Async and Await

The async and await keywords provide a cleaner syntax for handling Promises, allowing us to write asynchronous code that reads like synchronous code.

Basic Async/Await Usage

	•	async: Declares an asynchronous function.
	•	await: Pauses execution until the Promise is resolved.

Example:

async function fetchData() {
    try {
        let data = await somePromise();
        console.log(data);
    } catch (error) {
        console.error(error);
    }
}
fetchData();

Here:

	•	The function fetchData waits for somePromise to resolve and logs the result.
	•	If somePromise fails, catch handles the error.

Advanced Async/Await

We can use await with multiple promises using Promise.all() for parallel execution.

Example:

async function fetchData() {
    let [data1, data2] = await Promise.all([fetch(url1), fetch(url2)]);
    console.log(data1, data2);
}
fetchData();

In this case:

	•	Promise.all executes multiple fetches in parallel, making it faster than sequentially awaiting each fetch.

API Calls with fetch

The fetch API provides an easy way to make network requests and handle responses.

Basic Fetch Usage

fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error(error));

	•	fetch returns a Promise.
	•	response.json() parses JSON data, returning another Promise for the parsed result.
	•	Errors are caught in the catch block.

Using Fetch with Async/Await

You can handle fetch requests more cleanly with async/await.

Example:

async function getData() {
    try {
        let response = await fetch('https://api.example.com/data');
        let data = await response.json();
        console.log(data);
    } catch (error) {
        console.log("Error:", error);
    }
}
getData();

Handling Different HTTP Methods with fetch

fetch supports other HTTP methods like POST, PUT, DELETE, etc., by modifying the request options.

Example with POST:

fetch('https://api.example.com/data', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ name: "John", age: 30 })
})
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error(error));

In this example:

	•	We specify the HTTP method as POST.
	•	headers contain metadata such as Content-Type to tell the server about the data format.
	•	body contains the data we’re sending to the server, in JSON format.

Summary

This guide has covered:

	1.	Error Handling: Using try, catch, throw, and finally to handle exceptions.
	2.	Promises: Creating and chaining promises to manage asynchronous operations.
	3.	Async/Await: Cleaner syntax for handling promises.
	4.	Fetch API: Making API calls, handling different HTTP methods, and working with JSON data.

These techniques are essential for handling asynchronous operations and building stable applications in JavaScript. Let me know if you’d like further explanations or additional examples on any specific part!
