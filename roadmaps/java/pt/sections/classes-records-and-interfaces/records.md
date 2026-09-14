# Records

Record é class concisa para data carriers transparentes. O header declara components que viram fields final privados com accessors, e o compiler gera constructor, `equals`, `hashCode` e `toString`.

```java
public record User(long id, String name) {
    public User {
        Objects.requireNonNull(name);
    }
}
```

Records são shallowly immutable: o componente não pode ser reassigned, mas objeto mutável contido pode mudar. Use compact constructors para validar/normalizar valores.
