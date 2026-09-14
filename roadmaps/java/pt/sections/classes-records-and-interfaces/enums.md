# Enums

Enums Java são classes completas com conjunto fixo de instâncias. Podem ter fields, constructors, methods e comportamento por constant, além de integrar com `switch`, `EnumSet` e `EnumMap`.

```java
enum Status {
    PENDING,
    READY,
    FAILED
}

Status status = Status.READY;
```

Use enums para estados simbólicos fechados. Se cada estado carrega shapes muito diferentes, sealed hierarchy de records pode representar melhor que enum com vários fields nullable.
