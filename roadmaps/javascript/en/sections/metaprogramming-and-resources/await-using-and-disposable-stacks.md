# `await using` and Disposable Stacks

`await using` manages a resource whose asynchronous cleanup is provided by `[Symbol.asyncDispose]()`. Disposal is awaited when the scope exits, so the syntax is allowed only where `await` is allowed. Acquisition and cleanup can each involve asynchronous work.

```js
async function read(openFile) {
  await using file = await openFile();
  return file.read();
}

{
  using stack = new DisposableStack();
  stack.defer(() => console.log("cleanup"));
}
```

`DisposableStack` and `AsyncDisposableStack` collect several cleanup actions when ownership is easier to manage as a group. They preserve reverse-order cleanup and well-defined error behavior. The feature is opt-in: resources declared with ordinary `const` or `let` are not automatically disposed, so ownership conventions and correct registration remain essential.
