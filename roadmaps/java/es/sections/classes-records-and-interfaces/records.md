# Records

Un record es una class concisa para data carriers transparentes. El header declara components que se vuelven fields final privados con accessors, y el compiler genera constructor, `equals`, `hashCode` y `toString`.

```java
public record User(long id, String name) {
    public User {
        Objects.requireNonNull(name);
    }
}
```

Los records son shallowly immutable: el component no puede reasignarse, pero un objeto mutable contenido puede cambiar. Usa compact constructors para validar/normalizar valores.
