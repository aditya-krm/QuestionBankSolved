# Question:

21. Provide examples using callbacks, Promises, and async/await for Node.js

# Answer:

## Callbacks, Promises, and Async/Await in Node.js: Examples

Here's a breakdown of each approach with examples:

**1. Callbacks:**

*   Callbacks are functions passed as arguments to other functions, to be executed when the other function finishes its task. 
*   They are the oldest way to handle asynchronous operations in Node.js.

```javascript
const fs = require('fs');

fs.readFile('file.txt', 'utf-8', (err, data) => {
  if (err) {
    console.error(err);
  } else {
    console.log(data);
  }
});

console.log('This line will be printed before the file content.');
```

*   In this example, `fs.readFile` takes a callback function as its third argument. This callback function will be called with two arguments: `err` (error object) and `data` (file content). 
*   Notice how "This line..." is printed before the file content due to the asynchronous nature of the operation.

**2. Promises:**

*   Promises are objects that represent the eventual completion (or failure) of an asynchronous operation and its resulting value.
*   They offer a cleaner way to handle asynchronous code compared to callbacks, avoiding "callback hell."

```javascript
const fs = require('fs').promises;

fs.readFile('file.txt', 'utf-8')
  .then(data => {
    console.log(data);
  })
  .catch(err => {
    console.error(err);
  });
```

*   Here, `fs.promises.readFile` returns a Promise. We chain `.then` to handle the successful case (data) and `.catch` to handle errors.

**3. Async/Await:**

*   Async/await is a syntactic sugar built on top of promises, making asynchronous code look more like synchronous code.
*   It improves code readability and maintainability.

```javascript
const fs = require('fs').promises;

async function readFile() {
  try {
    const data = await fs.readFile('file.txt', 'utf-8');
    console.log(data);
  } catch (err) {
    console.error(err);
  }
}

readFile();
```

*   The `async` keyword defines an asynchronous function. Inside, we use `await` to wait for the promise returned by `fs.readFile` to resolve, and then assign the result to `data`.
*   Error handling is done with a `try...catch` block.

**Choosing the Right Approach:**

*   **Callbacks:** Useful for simple asynchronous operations but can lead to callback hell in complex scenarios.
*   **Promises:** Offer better code organization and error handling than callbacks.
*   **Async/Await:** Provides the most readable and maintainable way to write asynchronous code, especially when dealing with multiple asynchronous operations.

In modern Node.js development, Promises and Async/Await are generally preferred over callbacks for better code structure and readability. 
