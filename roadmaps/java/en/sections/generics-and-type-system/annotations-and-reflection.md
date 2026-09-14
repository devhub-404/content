# Annotations and Reflection

Annotations attach metadata to declarations and type uses, while reflection inspects classes, methods, fields, constructors, generic metadata, and annotations at runtime. Frameworks use both for serialization, dependency injection, testing, persistence, and plugins.

```java
@Deprecated
public void oldApi() { }

Class<?> type = User.class;
for (var method : type.getDeclaredMethods()) {
    System.out.println(method.getName());
}
```

Reflection trades compile-time safety and performance for flexibility. Prefer ordinary typed calls when the type set is known, and cache repeated metadata access in reflection-heavy infrastructure.
