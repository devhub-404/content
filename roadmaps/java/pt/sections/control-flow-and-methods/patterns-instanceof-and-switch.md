# Pattern Matching para `instanceof` e `switch`

Pattern matching combina type test com extração de variável. Patterns em `instanceof` evitam cast separado e `switch` pode despachar hierarquias por tipo e guards.

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

Ele é especialmente poderoso com records e sealed hierarchies porque o compiler conhece o state space fechado. Use para alternativas de domínio, não para substituir todo dispatch polimórfico.
