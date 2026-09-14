# Arrays y Varargs

Los arrays Java son objetos de length fijo con checks de element type en runtime y elementos zero-initialized. Varargs `T...` se implementa como un parámetro array y permite cero o más argumentos.

```java
int[] values = {10, 20, 30};

static int sum(int... values) {
    int total = 0;
    for (int value : values) total += value;
    return total;
}
```

Los arrays sirven para datos fijos y APIs low-level, mientras collections son más flexibles. Los generic arrays tienen restricciones porque arrays son reified en runtime y generics sufren type erasure.
