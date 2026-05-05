---
url: /docs/guide/usage/linter/rules/jest/no-alias-methods.md
---

### What it does

Enforces Jest's canonical matcher names instead of aliases.

### Why is this bad?

Jest matcher aliases are deprecated and are going to be removed in the next major version of Jest.
See [jestjs/jest#13164](https://github.com/jestjs/jest/issues/13164) for more.

This rule makes it easier to search for all occurrences of a matcher and ensures consistency among matcher names.

### Examples

Examples of **incorrect** code for this rule:

```javascript
expect(a).toBeCalled();
expect(a).toBeCalledTimes();
expect(a).toBeCalledWith();
expect(a).lastCalledWith();
expect(a).nthCalledWith();
expect(a).toReturn();
expect(a).toReturnTimes();
expect(a).toReturnWith();
expect(a).lastReturnedWith();
expect(a).nthReturnedWith();
expect(a).toThrowError();
```

Examples of **correct** code for this rule:

```javascript
expect(a).toHaveBeenCalled();
expect(a).toHaveBeenCalledTimes();
expect(a).toHaveBeenCalledWith();
expect(a).toHaveBeenLastCalledWith();
expect(a).toHaveBeenNthCalledWith();
expect(a).toHaveReturned();
expect(a).toHaveReturnedTimes();
expect(a).toHaveReturnedWith();
expect(a).toHaveLastReturnedWith();
expect(a).toHaveNthReturnedWith();
expect(a).toThrow();
```

## How to use

## Version

This rule was added in v0.0.12.

## References
