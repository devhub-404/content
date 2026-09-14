# `if`, `switch`, and Switch Expressions

`if` handles general Boolean branching, while modern `switch` can be either a statement or an expression that yields a value. Arrow labels avoid accidental fall-through, and switch expressions must be exhaustive.

```java
String label = switch (status) {
    case READY -> "ready";
    case FAILED -> "failed";
    case PENDING -> "pending";
};
```

Prefer switch expressions for a closed mapping from one input to one result. Classic colon-style switch remains useful in some imperative cases, but fall-through should be deliberate and obvious.
