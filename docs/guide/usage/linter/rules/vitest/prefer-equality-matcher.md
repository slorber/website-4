---
url: /docs/guide/usage/linter/rules/vitest/prefer-equality-matcher.md
---

### What it does

Jest has built-in matchers for expecting equality, which allow for more readable
tests and error messages if an expectation fails.

### Why is this bad?

Testing equality expressions with generic matchers like `toBe(true)`
makes tests harder to read and understand. When tests fail, the error
messages are less helpful because they don't show what the actual values
were. Using specific equality matchers provides clearer test intent and
better debugging information.

### Examples

Examples of **incorrect** code for this rule:

```javascript
expect(x === 5).toBe(true);
expect(name === "Carl").not.toEqual(true);
expect(myObj !== thatObj).toStrictEqual(true);
```

Examples of **correct** code for this rule:

```javascript
expect(x).toBe(5);
expect(name).not.toEqual("Carl");
expect(myObj).toStrictEqual(thatObj);
```

## How to use

## Version

This rule was added in v0.2.9.

## References
