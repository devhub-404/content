# Unmodifiable Collections and Copies

Factory methods such as `List.of`, `Set.of`, and `Map.of` create unmodifiable collections, while `copyOf` creates an unmodifiable snapshot-like copy according to its contract. An unmodifiable collection prevents structural mutation through that reference but does not automatically deep-freeze mutable elements.

```java
List<String> names = List.of("Ada", "Mina");
List<String> snapshot = List.copyOf(source);
```

Use these factories for constants, return values, and boundaries where callers should not mutate the collection. Distinguish an unmodifiable view from an independent copy when changes to the backing collection could otherwise leak through.
