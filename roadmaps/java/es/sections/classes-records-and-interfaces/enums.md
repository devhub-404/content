# Enums

Los enums Java son classes completas con un conjunto fijo de instancias. Pueden tener fields, constructors, methods y comportamiento por constant, además de integrarse con `switch`, `EnumSet` y `EnumMap`.

```java
enum Status {
    PENDING,
    READY,
    FAILED
}

Status status = Status.READY;
```

Usa enums para estados simbólicos cerrados. Si cada estado lleva shapes muy distintos, una sealed hierarchy de records puede modelar mejor que un enum con muchos fields nullable.
