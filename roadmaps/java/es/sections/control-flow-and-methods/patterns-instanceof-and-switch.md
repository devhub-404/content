# Pattern Matching para `instanceof` y `switch`

Pattern matching combina type test con extracción de variable. Los patterns en `instanceof` evitan un cast separado y `switch` puede despachar jerarquías por tipo y guards.

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

Es especialmente potente con records y sealed hierarchies porque el compiler conoce el state space cerrado. Úsalo para alternativas de dominio, no para sustituir todo dispatch polimórfico.
