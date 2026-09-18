# JavaScript Execution and Asynchronous Programming

## 1. How Does JavaScript Execute Code?

JavaScript executes code using a JavaScript engine such as V8.
It is single-threaded, so it executes one task at a time using the call stack.
Functions are added to the call stack when called and removed after execution.

Example:
```javascript
console.log("Hello");
console.log("World");
```

## 2. Synchronous vs Asynchronous Code

Synchronous code runs line by line, and each operation waits for the previous one to finish.
Asynchronous code allows other code to continue while a task is being completed.

Example:
```javascript
console.log("Start");

setTimeout(() => console.log("Async"), 1000);

console.log("End");
```

## 3. Ways to Make Code Asynchronous

JavaScript commonly handles asynchronous operations using callbacks, Promises, and async/await.
Browser APIs such as timers, Fetch, and events can also perform asynchronous operations.

Example:
```javascript
setTimeout(() => {
    console.log("Executed later");
}, 1000);
```

## 4. What Are Web Browser APIs?

Web Browser APIs are features provided by the browser environment for JavaScript.
Examples include DOM, Fetch API, setTimeout(), Web Storage, and Geolocation.
They handle tasks that are outside the core JavaScript engine.

Example:
```javascript
setTimeout(() => {
    console.log("Timer finished");
}, 1000);
```

## 5. What Is the Event Loop?

The event loop coordinates the call stack and task queues.
It checks whether the call stack is empty and moves ready callbacks to the stack.
Promise callbacks use the microtask queue, which is processed before the regular task queue.

Example:
```javascript
console.log("A");

setTimeout(() => console.log("B"), 0);

console.log("C");
```

Output:
```text
A
C
B
```

## 6. What Is Callback Hell?

Callback hell occurs when multiple asynchronous callbacks are nested inside one another.
This creates deeply nested code that becomes difficult to read, maintain, and debug.

Example:
```javascript
login(() => {
    getProfile(() => {
        getPosts(() => {
            console.log("Done");
        });
    });
});
```

## 7. What Is Inversion of Control in Callbacks?

Inversion of control means giving another function or API control over when a callback is executed.
For example, `setTimeout()` decides when the provided callback will run.
This can be risky if the callback is called incorrectly, multiple times, or never called.

Example:
```javascript
setTimeout(() => {
    console.log("Task completed");
}, 1000);
```
