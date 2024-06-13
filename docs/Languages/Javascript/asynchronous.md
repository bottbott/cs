## Callbacks

Callbacks are functions passed into other functions as arguments. They come in two timing varieties where they execute synchronously or asynchronously. Synchronous callbacks execute immediately, while asynchronous callbacks execute at a later time.

```typescript
function callback() {
  console.log("Hello, World!");
}

function higherOrderFunction(callback: () => void) {
  callback();
}

higherOrderFunction(callback);
```

Event handlers are commonly used to handle interactions with the user interface in browser, and are a type of callback.

### Callback Hell

When we write synchronous code we can easiliy string functions together in a way that is easy to follow, but if we have a series of asynchronous functions that depend on the result of the previous function, we can end up with a pyramid of doom.

```typescript
function callback1(callback2: () => void) {
  setTimeout(() => {
    console.log("First callback");
    callback2();
  }, 1000);
}

function callback2(callback3: () => void) {
  setTimeout(() => {
    console.log("Second callback");
    callback3();
  }, 1000);
}

function callback3() {
  setTimeout(() => {
    console.log("Third callback");
  }, 1000);
}

callback1(() => {
  callback2(() => {
    callback3();
  });
});
```

The code can be much harder to follow, and error handling becomes more difficult as we must handle errors at each level of the pyramid.

```typescript
function callback1(callback2: () => void) {
  setTimeout(() => {
    console.log("First callback");
    callback2();
  }, 1000);
}

function callback2(callback3: () => void) {
  setTimeout(() => {
    console.log("Second callback");
    callback3();
  }, 1000);
}

function callback3() {
  setTimeout(() => {
    console.log("Third callback");
    throw new Error("Error in callback3");
  }, 1000);
}

callback1(() => {
  callback2(() => {
    try {
      callback3();
    } catch (error) {
      console.error(error);
    }
  });
});
```

## Promises

Promises were introduced to have an easier to read and write way of handling asynchronous code. A promise is an object. That object will produce a single value some time in the future. It could be a resolved value, or a reason that it’s not resolved (rejected).

```typescript
function promise1() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("First promise");
      resolve();
    }, 1000);
  });
}

function promise2() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Second promise");
      resolve();
    }, 1000);
  });
}

function promise3() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Third promise");
      resolve();
    }, 1000);
  });
}

promise1()
  .then(() => promise2())
  .then(() => promise3())
  .catch((error) => console.error(error));
```

There are a few key terms about promises that are important to understand:

Verbs:

- fulfill: to settle a promise with a fulfillment value
- reject: to settle a promise with a rejection reason
- settle: to either fulfill or reject a promise
- resolve: either
  - to fulfill a promise with a fulfillment value (resolve with)
  - make a promise follow another promise, adopting its eventual state and value (resolve to)

State:

- pending: initial state, neither fulfilled nor rejected.
- fulfilled: meaning that the operation completed successfully. The promise has been fulfilled and now has a value.
- rejected: meaning that the operation failed.

Other:

- settled: The promise is either fulfilled or rejected, but not pending.
- resolved: either settled or following another promise that will determine its state.
- unresolved: not settled, meaning it is pending.

## Async/Await

The async keyword can be applied to a function to make it return a promise. You can also use the async keyword in a function expression so that it executes an Immediatelly Invoked Function Expression (IIFE).

The await keyword is used within async functions to pause the execution of the function until the promise is resolved.

```typescript
function promise1() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("First promise");
      resolve();
    }, 1000);
  });
}

function promise2() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Second promise");
      resolve();
    }, 1000);
  });
}

function promise3() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Third promise");
      resolve();
    }, 1000);
  });
}

async function main() {
  try {
    await promise1();
    await promise2();
    await promise3();
  } catch (error) {
    console.error(error);
  }
}

main();
```
