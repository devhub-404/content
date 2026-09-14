# Interfaces y Default Methods

Las interfaces definen contratos de comportamiento y soportan múltiples implementaciones de interfaces. Los default methods añaden comportamiento reutilizable sin obligar a cada implementación a cambiar y los methods static/private ayudan con implementación interna.

```java
interface Clock {
    Instant now();

    default boolean isPast(Instant value) {
        return value.isBefore(now());
    }
}
```

Prefiere interfaces pequeñas por capacidad. Los default methods ayudan a evolucionar APIs, pero varias interfaces pueden crear conflictos, así que mantén la inheritance comprensible.
