# Async Testing

## Topics
- [done()](#done)

## Overview 

- Asynchronous code doesn’t execute directly within the current flow of code. Because the code runs on a different thread or dispatch queue.

- As async programs runs in a different thread, we get unexpected result while testing those programs.

- Like sync testing there is also some methods to test async programs.

## done()
- When our code is async we have to tell to tell explicitly that when the excecution is done show the test result.
- For that we use `done` method.

### Example :-

```javascript
const delayOutput = (content, callback) => {
  setTimeout(() => {
    callback(content)
  }, 2000);
}
```

Here is an async function. It will call the call back function after 2 sec. So we have to tell when the whole excecution is completed then show the test results.

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

- `done` is the second argument of the annoynomous function of `it`.
- we have to call `done()` before assert.

### [⬆ Top](#async-testing)
### [⬅ Back](/index.md)