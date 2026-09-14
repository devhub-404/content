# Memory and Garbage Collection

JavaScript runtimes manage ordinary memory automatically. Conceptually, values reachable from active roots can stay alive, while unreachable values become eligible for garbage collection. The exact algorithm and timing are implementation details; program correctness must never depend on collection running at a particular moment.

```js
let cache = new Map();

function remember(key, value) {
  cache.set(key, value);
}

function clearCache() {
  cache = new Map();
}
```

Leaks in managed languages are usually accidental reachability: long-lived Maps, arrays, closures, listeners, or caches keep data reachable after it is no longer useful. Weak collections can help with identity-associated metadata, but they do not replace lifecycle design. Use memory profiling tools to find retained objects instead of attempting to manually free normal objects.
