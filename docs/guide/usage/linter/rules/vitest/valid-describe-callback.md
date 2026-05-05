---
url: /docs/guide/usage/linter/rules/vitest/valid-describe-callback.md
---

### What it does

This rule validates that the second parameter of a `describe()` function is a
callback function. This callback function:

* should not be
  [async](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
* should not contain any parameters
* should not contain any `return` statements

### Why is this bad?

Using an improper `describe()` callback function can lead to unexpected test
errors.

### Examples

Examples of **incorrect** code for this rule:

```javascript
// Async callback functions are not allowed
describe("myFunction()", async () => {
  // ...
});

// Callback function parameters are not allowed
describe("myFunction()", (done) => {
  // ...
});

// Returning a value from a describe block is not allowed
describe("myFunction", () =>
  it("returns a truthy value", () => {
    expect(myFunction()).toBeTruthy();
  }));
```

## How to use

## Version

This rule was added in v0.0.8.

## References
