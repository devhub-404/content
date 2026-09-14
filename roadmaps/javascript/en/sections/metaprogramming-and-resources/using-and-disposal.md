# `using` and Explicit Disposal

A `using` declaration binds a disposable resource and automatically calls its `[Symbol.dispose]()` method when the lexical scope exits. Cleanup runs for normal completion and abrupt exits such as errors, returns, breaks, or continues. Multiple resources in the same scope are disposed in reverse declaration order.

```js
class Lock {
  acquire() {
    console.log("locked");
    return this;
  }

  [Symbol.dispose]() {
    console.log("unlocked");
  }
}

{
  using lock = new Lock().acquire();
  // protected work
}
```

This is explicit resource management for locks, handles, subscriptions, or other resources whose external lifetime matters; it is not a replacement for garbage collection. The resource must implement the disposable protocol, though nullish values are allowed. A `using` binding cannot be reassigned, and ownership still matters if another reference to the disposed object escapes the scope.
