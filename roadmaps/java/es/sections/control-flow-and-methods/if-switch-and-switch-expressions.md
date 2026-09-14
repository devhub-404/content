# `if`, `switch` y Switch Expressions

`if` maneja branching Boolean general, mientras el `switch` moderno puede ser statement o expression que produce un valor. Los arrow labels evitan fall-through accidental y las switch expressions deben ser exhaustivas.

```java
String label = switch (status) {
    case READY -> "ready";
    case FAILED -> "failed";
    case PENDING -> "pending";
};
```

Prefiere switch expression para un mapping cerrado de una entrada a un resultado. El switch clásico sigue siendo útil en casos imperativos, pero el fall-through debe ser deliberado.
