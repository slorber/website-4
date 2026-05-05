---
url: /docs/guide/usage/linter/rules/vitest/prefer-strict-equal.md
---

### What it does

This rule triggers a warning if `toEqual()` is used to assert equality.

### Why is this bad?

The `toEqual()` matcher performs a deep equality check but ignores
`undefined` values in objects and arrays. This can lead to false
positives where tests pass when they should fail. `toStrictEqual()`
provides more accurate comparison by checking for `undefined` values.

### Examples

Examples of **incorrect** code for this rule:

```javascript
expect({ a: "a", b: undefined }).toEqual({ a: "a" });
```

Examples of **correct** code for this rule:

```javascript
expect({ a: "a", b: undefined }).toStrictEqual({ a: "a" });
```

## How to use

## Version

This rule was added in v0.2.13.

## References
