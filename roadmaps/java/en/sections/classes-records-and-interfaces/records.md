# Records

A record is a concise class for transparent data carriers. Its header declares components that become private final fields with accessors, and the compiler generates a constructor, `equals`, `hashCode`, and `toString` based on those components.

```java
public record User(long id, String name) {
    public User {
        Objects.requireNonNull(name);
    }
}
```

Records are shallowly immutable: a record reference cannot replace a component, but a mutable object stored in a component can still change internally. Use compact constructors to validate or normalize component values.
