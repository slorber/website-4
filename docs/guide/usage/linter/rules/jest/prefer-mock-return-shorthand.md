---
url: /docs/guide/usage/linter/rules/jest/prefer-mock-return-shorthand.md
---

### What it does

When working with mocks of functions that return simple values, Jest provides some API sugar functions to reduce the amount of boilerplate you have to write.

### Why is this bad?

Not using Jest's API sugar functions adds unnecessary boilerplate and makes tests harder to read. These helpers clearly express intent
and reduce errors, keeping tests simple and maintainable.

### Examples

Examples of **incorrect** code for this rule:

```js
jest.fn().mockImplementation(() => "hello world");

jest
  .spyOn(fs.promises, "readFile")
  .mockImplementationOnce(() => Promise.reject(new Error("oh noes!")));

myFunction
  .mockImplementationOnce(() => 42)
  .mockImplementationOnce(() => Promise.resolve(42))
  .mockReturnValue(0);
```

Examples of **correct** code for this rule:

```js
jest.fn().mockResolvedValue(123);

jest.spyOn(fs.promises, "readFile").mockReturnValue(Promise.reject(new Error("oh noes!")));
jest.spyOn(fs.promises, "readFile").mockRejectedValue(new Error("oh noes!"));

jest.spyOn(fs, "readFileSync").mockImplementationOnce(() => {
  throw new Error("oh noes!");
});

myFunction.mockResolvedValueOnce(42).mockResolvedValueOnce(42).mockReturnValue(0);
```

## How to use

## Version

This rule was added in v1.49.0.

## References
