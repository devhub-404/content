# Weak Collections

`WeakMap` and `WeakSet` hold eligible keys weakly, so the collection does not by itself keep a key alive for garbage collection. `WeakMap` is useful for attaching auxiliary metadata to object identity; `WeakSet` tracks weak membership.

```js
const metadata = new WeakMap();

function attachMetadata(element, data) {
  metadata.set(element, data);
}

function getMetadata(element) {
  return metadata.get(element);
}
```

Weak collections intentionally cannot be enumerated and expose no `size`, because garbage collection is nondeterministic. They are therefore unsuitable for collections that must be listed or counted. Their purpose is lifecycle-friendly association, not automatic resource cleanup; external handles, listeners, and subscriptions still need explicit ownership and disposal.
