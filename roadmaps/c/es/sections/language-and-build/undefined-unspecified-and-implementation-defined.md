# Comportamiento Undefined, Unspecified e Implementation-defined

El estándar C deja deliberadamente ciertos comportamientos undefined, unspecified o implementation-defined. Undefined behavior no impone requisitos después de la operación inválida, por lo que el compilador puede optimizar suponiendo que nunca sucede. Overflow de enteros signed, dereference de punteros inválidos y muchos accesos fuera de límites son ejemplos importantes.

```c
#include <limits.h>

int add_one(int x) {
    if (x == INT_MAX) {
        /* handle overflow deliberately */
        return x;
    }
    return x + 1;
}
```

El comportamiento implementation-defined debe documentarse por la implementación, mientras unspecified permite varios resultados válidos sin exigir cuál se elige. El C portable evita depender de UB y aísla las suposiciones de plataforma detrás de interfaces comprobadas o configuración.
