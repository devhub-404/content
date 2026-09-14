# Punteros a Función y Callbacks

Las funciones pueden referenciarse mediante punteros a función y pasarse como callbacks. Así APIs como `qsort` reciben comportamiento del caller y muchas bibliotecas C modelan handlers, políticas e interfaces de plugin.

```c
typedef int (*compare_fn)(const void *, const void *);

int compare_ints(const void *a, const void *b) {
    const int left = *(const int *)a;
    const int right = *(const int *)b;
    return (left > right) - (left < right);
}
```

El tipo del puntero debe coincidir con la firma real. Callbacks genéricos con `void *` trasladan parte del control de tipos a casts dentro del callback, por lo que el contrato debe documentarse bien. Typedefs de dominio hacen estas APIs más legibles.
