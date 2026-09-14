# `Iterable`, `Iterator`, and Traversal

`Iterable` represents something that can produce an iterator, and enhanced `for` uses that protocol. `Iterator` exposes `hasNext`, `next`, and optional removal semantics. Spliterators provide richer traversal support used by streams and parallel decomposition.

```java
Iterator<String> it = names.iterator();
while (it.hasNext()) {
    String name = it.next();
    if (name.isBlank()) it.remove();
}
```

Use iterator removal only when the implementation supports it and the mutation belongs to the traversal. For ordinary transformations, stream operations or collection methods can express intent more clearly.
