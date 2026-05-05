---
url: /docs/guide/usage/linter/rules/jest/consistent-test-it.md
---

### What it does

Jest allows you to choose how you want to define your tests, using the `it` or
the `test` keywords, with multiple permutations for each:

* **it:** `it`, `xit`, `fit`, `it.only`, `it.skip`.
* **test:** `test`, `xtest`, `test.only`, `test.skip`.

### Why is this bad?

It's a good practice to be consistent in your test suite, so that all tests are written in the same way.

## Configuration

This rule accepts a configuration object with the following properties:

### fn

type: `"it" | "test"`

default: `"test"`

Decides whether to use `test` or `it`.

Examples of **incorrect** code for `{ "fn": "test" }`:

```javascript
it("foo");
it.only("foo");
```

Examples of **correct** code for `{ "fn": "test" }`:

```javascript
test("foo");
test.only("foo");
```

Examples of **incorrect** code for `{ "fn": "it" }`:

```javascript
test("foo");
test.only("foo");
```

Examples of **correct** code for `{ "fn": "it" }`:

```javascript
it("foo");
it.only("foo");
```

### withinDescribe

type: `"it" | "test"`

default: `"it"`

Decides whether to use `test` or `it` within a `describe` scope.
If only `fn` is provided, this will default to the value of `fn`.

Examples of **incorrect** code for `{ "withinDescribe": "test" }`:

```javascript
describe("foo", function () {
  it("bar");
});
```

Examples of **correct** code for `{ "withinDescribe": "test" }`:

```javascript
describe("foo", function () {
  test("bar");
});
```

## How to use

## Version

This rule was added in v0.5.3.

## References
