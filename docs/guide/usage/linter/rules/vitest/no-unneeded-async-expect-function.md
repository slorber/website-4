---
url: /docs/guide/usage/linter/rules/vitest/no-unneeded-async-expect-function.md
---

### What it does

Disallows unnecessary async function wrapper for expected promises.

### Why is this bad?

When the only statement inside an async wrapper is `await someCall()`,
the call should be passed directly to `expect` instead. This makes the
test code more concise and easier to read.

### Examples

Examples of **incorrect** code for this rule:

```js
await expect(async () => {
  await doSomethingAsync();
}).rejects.toThrow();

await expect(async () => await doSomethingAsync()).rejects.toThrow();
```

Examples of **correct** code for this rule:

```js
await expect(doSomethingAsync()).rejects.toThrow();
```

## How to use

## Version

This rule was added in v1.39.0.

## References
