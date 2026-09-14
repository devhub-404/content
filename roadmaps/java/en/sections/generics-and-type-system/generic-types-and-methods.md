# Generic Types and Methods

Generics let classes, interfaces, and methods preserve type relationships without casts. A type parameter represents a compile-time type variable, while Java implements most generics through type erasure rather than reified runtime specialization.

```java
public final class Box<T> {
    private final T value;
    public Box(T value) { this.value = value; }
    public T value() { return value; }
}

static <T> T first(List<T> values) {
    return values.getFirst();
}
```

Use generics when a relationship between inputs, stored values, and outputs matters. Avoid raw types, which discard type safety and force unchecked conversions into code that could otherwise be verified.
