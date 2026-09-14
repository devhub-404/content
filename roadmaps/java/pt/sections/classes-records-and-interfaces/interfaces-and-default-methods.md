# Interfaces e Default Methods

Interfaces definem contratos de comportamento e suportam múltiplas implementações de interface. Default methods adicionam comportamento reutilizável sem obrigar toda implementação a mudar, e methods static/private ajudam implementação interna.

```java
interface Clock {
    Instant now();

    default boolean isPast(Instant value) {
        return value.isBefore(now());
    }
}
```

Prefira interfaces pequenas por capacidade. Default methods ajudam evolução de API, mas múltiplas interfaces podem criar conflitos, então mantenha inheritance compreensível.
