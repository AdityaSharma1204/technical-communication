# JavaScript Promises

## 1. What Is a Promise?

A Promise is an object that represents the eventual result of an asynchronous operation.
It can either be successfully completed or failed.
Promises help handle asynchronous code in a cleaner way than nested callbacks.

Example:
```javascript
const promise = fetch("https://example.com");
```

## 2. How to Create a New Promise?

A new Promise is created using the `Promise` constructor.
It takes a function with two parameters: `resolve` and `reject`.
`resolve()` is called when the operation succeeds, and `reject()` is called when it fails.

Example:
```javascript
const promise = new Promise((resolve, reject) => {
    const success = true;

    if (success) {
        resolve("Task completed");
    } else {
        reject("Task failed");
    }
});
```

## 3. What Are the Different States of a Promise?

A Promise has three states:
1. `pending` - The operation is still in progress.
2. `fulfilled` - The operation completed successfully.
3. `rejected` - The operation failed.

A Promise starts as `pending` and changes to either `fulfilled` or `rejected`.

Example:
```javascript
const promise = new Promise((resolve) => {
    resolve("Success");
});
```

## 4. How to Consume an Existing Promise?

An existing Promise can be consumed using `.then()`, `.catch()`, and `.finally()`.
`then()` handles a fulfilled Promise, while `catch()` handles a rejected Promise.
`finally()` runs after the Promise is settled, regardless of the result.

Example:
```javascript
promise
    .then(result => console.log(result))
    .catch(error => console.log(error))
    .finally(() => console.log("Completed"));
```