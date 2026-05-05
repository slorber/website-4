---
url: /docs/guide/usage/linter/rules/vitest/no-test-return-statement.md
---

### What it does

Disallow explicitly returning from tests.

### Why is this bad?

Tests in Jest should be void and not return values.
If you are returning Promises then you should update the test to use
`async/await`.

### Examples

Examples of **incorrect** code for this rule:

```javascript
test("one", () => {
  return expect(1).toBe(1);
});
```

Examples of **correct** code for this rule:

```javascript
test("one", () => {
  expect(1).toBe(1);
});
```

## How to use

## Version

This rule was added in v0.2.0.

## References
