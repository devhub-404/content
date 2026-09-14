# Pattern Matching for `instanceof` and `switch`

Pattern matching combines a type test with variable extraction and can make data-oriented branching safer and shorter. `instanceof` patterns avoid a separate cast, and `switch` patterns can dispatch over type hierarchies with guards.

```java
static String describe(Object value) {
    return switch (value) {
        case Integer n when n > 0 -> "positive int";
        case String s -> "string: " + s;
        case null -> "null";
        default -> "other";
    };
}
```

Pattern matching becomes especially powerful with records and sealed hierarchies because the compiler can reason about the closed state space. Use it to express domain alternatives, not as a replacement for every polymorphic method call.
