# Async Testing

## Topics
- [done()](#done)
- [mock function](#mock-function)

## Overview 

- Asynchronous code doesn’t execute directly within the current flow of code. Because the code runs on a different thread or dispatch queue.

- As async programs run in a different thread, we get unexpected result while testing those programs.

- Like sync testing there is also some methods to test async programs.

## done()
- When our code is async we have to tell to tell explicitly that when the execution is done show the test result.
- For that we use `done` method.

### Example :-

```javascript
const delayOutput = (content, callback) => {
  setTimeout(() => {
    callback(content)
  }, 2000);
}
```

Here is an async function. It will call the call back function after 2 sec. So we have to tell when the whole execution is completed then show the test results.

```javascript
describe("delayOutput", () => {
  it("should return same content", (_, done) => {
    delayOutput(2, (content) => {
      done();
      strictEqual(2, content);
    });
  });
});
```

- `done` is the second argument of the anonymous function of `it`.
- we have to call `done()` before assert.

## mock function

- **mock** means something that is not real but appearing or pretending to be exactly like something.
- mock functions are used to test behavior of any function, function is called with proper arguments or not.

## Example:

```javascript
const myFilter = (numbers, predicate) => numbers.filter(predicate);
```

Here is a function `myFilter` that takes two arguments, `numbers` and a `predicate`. I want to test that the predicate is called with proper arguments or not.



### [⬆ Top](#async-testing)
### [⬅ Back](/index.md)