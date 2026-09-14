# Tipos y Métodos Genéricos

Los generics permiten que classes, interfaces y methods conserven relaciones de tipo sin casts. Un type parameter es una variable de compile time y Java implementa la mayoría de generics mediante type erasure.

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

Usa generics cuando importe una relación entre inputs, almacenamiento y outputs. Evita raw types, que descartan seguridad e introducen unchecked conversions.
