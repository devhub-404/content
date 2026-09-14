# Tipos e Métodos Genéricos

Generics permitem que classes, interfaces e methods preservem relações de tipo sem casts. Type parameter é variável de compile time, e Java implementa a maioria dos generics por type erasure.

```java
public final class Box<T> {
    private final T value;
    public Box(T value) { this.value = value; }
    public T value() { return value; }
}

static <T> T first(List<T> values) {
    return values.getFirst();
}
```

Use generics quando uma relação entre inputs, storage e outputs importa. Evite raw types, que descartam segurança e introduzem unchecked conversions.
