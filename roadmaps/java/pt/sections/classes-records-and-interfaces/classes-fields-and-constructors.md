# Classes, Fields e Constructors

Classes combinam fields, constructors, methods, nested types e access control. Constructors estabelecem invariante inicial, enquanto fields `final` ajudam objetos cujo estado de identidade não muda após construção.

```java
public final class Account {
    private final String owner;
    private BigDecimal balance = BigDecimal.ZERO;

    public Account(String owner) {
        this.owner = Objects.requireNonNull(owner);
    }
}
```

Mantenha fields private salvo constants ou carriers deliberados. Valide invariantes na construção para que methods operem sobre objetos válidos sem repetir checks básicos.
