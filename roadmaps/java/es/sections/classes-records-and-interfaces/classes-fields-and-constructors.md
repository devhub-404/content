# Classes, Fields y Constructors

Las classes combinan fields, constructors, methods, nested types y access control. Los constructors establecen la invariante inicial, mientras fields `final` ayudan con objetos cuyo estado de identidad no cambia tras la construcción.

```java
public final class Account {
    private final String owner;
    private BigDecimal balance = BigDecimal.ZERO;

    public Account(String owner) {
        this.owner = Objects.requireNonNull(owner);
    }
}
```

Mantén fields private salvo constants o carriers deliberados. Valida invariantes en construcción para que los methods operen sobre objetos válidos sin repetir checks básicos.
