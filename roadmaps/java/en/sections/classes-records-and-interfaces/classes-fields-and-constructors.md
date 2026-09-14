# Classes, Fields, and Constructors

Classes combine fields, constructors, methods, nested types, and access control. Constructors establish the initial object invariant, while `final` fields support objects whose identity-bearing state does not change after construction.

```java
public final class Account {
    private final String owner;
    private BigDecimal balance = BigDecimal.ZERO;

    public Account(String owner) {
        this.owner = Objects.requireNonNull(owner);
    }
}
```

Keep fields private unless they are true constants or simple data carriers with a deliberate public representation. Validate invariants during construction so methods can operate on a valid object rather than repeatedly rechecking basic state.
