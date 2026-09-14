# Enums

Java enums are full classes with a fixed set of instances. They can have fields, constructors, methods, and per-constant behavior, while also working naturally with `switch`, `EnumSet`, and `EnumMap`.

```java
enum Status {
    PENDING,
    READY,
    FAILED
}

Status status = Status.READY;
```

Use enums for closed symbolic states and options. If each state carries different data shapes, a sealed hierarchy of records may model the domain more clearly than an enum with many nullable fields.
