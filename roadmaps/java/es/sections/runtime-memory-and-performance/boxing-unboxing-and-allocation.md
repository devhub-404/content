# Boxing, Unboxing y Allocation

Boxing convierte primitive en wrapper y unboxing hace lo contrario. Las generic collections almacenan reference types, así que `List<Integer>` usa wrappers, no una specialization de `int` en Java 25 normal.

```java
Integer boxed = 42;
int value = boxed;

List<Integer> values = List.of(1, 2, 3);
```

No optimices todo boxing por instinto, pero conoce allocation y riesgo de unbox de null en hot paths. Perfila antes de rediseñar APIs con primitive arrays o libraries especializadas.
