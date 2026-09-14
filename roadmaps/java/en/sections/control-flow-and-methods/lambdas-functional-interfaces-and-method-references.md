# Lambdas, Functional Interfaces, and Method References

A functional interface has one abstract method and can be implemented by a lambda or method reference. `java.util.function` provides common shapes such as `Predicate`, `Function`, `Consumer`, and `Supplier`.

```java
Predicate<String> nonEmpty = s -> !s.isEmpty();
Function<String, Integer> length = String::length;

names.stream()
    .filter(nonEmpty)
    .map(length)
    .forEach(System.out::println);
```

Captured local variables must be final or effectively final, which keeps closure state more predictable. Use functional interfaces where behavior is naturally passed as data; ordinary named methods and classes remain clearer for large stateful responsibilities.
