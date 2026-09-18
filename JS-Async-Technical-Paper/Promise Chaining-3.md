# Promise Chaining

## 1. How to Chain Promises Using `.then()`

Promise chaining means executing multiple asynchronous operations one after another.
Each `.then()` receives the value returned by the previous `.then()`.
The returned value can be passed to the next step in the chain.

Example:
```javascript
Promise.resolve(10)
    .then(value => value * 2)
    .then(value => console.log(value)); // 20
```

## 2. How to Handle Errors Using `.catch()`

`.catch()` is used to handle a rejected Promise or an error thrown in the chain.
It prevents the error from remaining unhandled.

Example:
```javascript
Promise.reject("Something went wrong")
    .catch(error => console.log(error));
```

## 3. `finally()` in a Promise Chain

`finally()` executes after a Promise is settled, whether it is fulfilled or rejected.
It is commonly used for cleanup operations.

Example:
```javascript
promise
    .then(result => console.log(result))
    .catch(error => console.log(error))
    .finally(() => console.log("Finished"));
```

## 4. Error Thrown Inside `.then()` With `.catch()`

If an error is thrown inside `.then()`, the Promise returned by that `.then()` becomes rejected.
A following `.catch()` can catch and handle that error.

Example:
```javascript
Promise.resolve()
    .then(() => {
        throw new Error("Failed");
    })
    .catch(error => console.log(error.message));
```

## 5. Error Thrown Inside `.then()` Without `.catch()`

If an error is thrown and there is no `.catch()`, the Promise becomes rejected without a handler.
This results in an unhandled Promise rejection.

Example:
```javascript
Promise.resolve()
    .then(() => {
        throw new Error("Failed");
    });
```

## 6. Why Place `.catch()` Towards the End?

Placing `.catch()` towards the end allows one handler to catch errors from multiple steps in the chain.
An error in any previous `.then()` can propagate to the nearest `.catch()`.

Example:
```javascript
task1()
    .then(task2)
    .then(task3)
    .catch(error => console.log(error));
```

## 7. How to Consume Multiple Promises by Chaining?

Promises can be chained when one operation depends on the result of the previous operation.
Return the next Promise from `.then()` to execute it after the previous one completes.

Example:
```javascript
getUser()
    .then(user => getPosts(user.id))
    .then(posts => console.log(posts))
    .catch(error => console.log(error));
```

## 8. How to Consume Multiple Promises Using `Promise.all()`?

`Promise.all()` runs multiple Promises concurrently and waits for all of them to fulfill.
It returns an array of results in the same order as the input Promises.
If any Promise rejects, `Promise.all()` rejects immediately.

Example:
```javascript
Promise.all([promise1, promise2, promise3])
    .then(results => console.log(results))
    .catch(error => console.log(error));
```

## 9. How to Do Error Handling With Promises?

Use `.catch()` to handle rejected Promises and errors thrown during the chain.
With `async/await`, use `try...catch` to handle errors.

Example:
```javascript
fetchData()
    .then(data => console.log(data))
    .catch(error => console.log(error));
```

## 10. Why Is Error Handling Important?

Asynchronous operations can fail because of network problems, invalid data, or other runtime errors.
Proper error handling prevents unhandled rejections and unexpected application behavior.
It also allows the program to provide a meaningful response when something fails.

## 11. How to Promisify a Callback-Based Function?

Promisification means converting a callback-based asynchronous function into a function that returns a Promise.
The callback's success result is passed to `resolve()`, and the error is passed to `reject()`.

Example using `setTimeout()`:
```javascript
function delay(time) {
    return new Promise(resolve => {
        setTimeout(resolve, time);
    });
}

delay(1000).then(() => console.log("Done"));
```

## 12. Promisifying `fs.readFile()`

Node.js callback-based functions can be converted into Promise-based functions.
Node.js also provides `fs.promises`, which is the preferred Promise-based API for file operations.

Example:
```javascript
const fs = require("fs");

function readFilePromise(fileName) {
    return new Promise((resolve, reject) => {
        fs.readFile(fileName, "utf8", (error, data) => {
            if (error) {
                reject(error);
            } else {
                resolve(data);
            }
        });
    });
}
```

## 13. `Promise.resolve()`

`Promise.resolve()` creates a fulfilled Promise with the given value.
It is useful when a normal value needs to be treated as a Promise.

Example:
```javascript
Promise.resolve("Hello")
    .then(value => console.log(value));
```

## 14. `Promise.reject()`

`Promise.reject()` creates an already rejected Promise.
It is useful for creating or returning a rejected Promise.

Example:
```javascript
Promise.reject("Failed")
    .catch(error => console.log(error));
```

## 15. `Promise.all()`

`Promise.all()` waits for all provided Promises to fulfill.
If any Promise rejects, the returned Promise rejects.

Example:
```javascript
Promise.all([promise1, promise2])
    .then(results => console.log(results))
    .catch(error => console.log(error));
```

## 16. `Promise.allSettled()`

`Promise.allSettled()` waits for all Promises to finish, whether fulfilled or rejected.
It returns the status and result of every Promise.

Example:
```javascript
Promise.allSettled([promise1, promise2])
    .then(results => console.log(results));
```

## 17. `Promise.any()`

`Promise.any()` fulfills as soon as the first Promise fulfills.
It ignores rejected Promises unless all provided Promises reject.

Example:
```javascript
Promise.any([promise1, promise2])
    .then(result => console.log(result))
    .catch(error => console.log(error));
```

## 18. `Promise.race()`

`Promise.race()` settles as soon as the first Promise settles.
Therefore, the first Promise to either fulfill or reject determines the result.

Example:
```javascript
Promise.race([promise1, promise2])
    .then(result => console.log(result))
    .catch(error => console.log(error));
```