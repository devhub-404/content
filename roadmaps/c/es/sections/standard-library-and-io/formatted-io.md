# I/O Formateado

Las funciones de la familia `printf` formatean valores según una format string y las de `scanf` hacen parsing hacia direcciones proporcionadas por el caller. Los specifiers deben corresponder a los tipos reales; un mismatch en I/O variádico puede producir undefined behavior.

```c
#include <stdio.h>

int age = 0;
if (scanf("%d", &age) == 1) {
    printf("age = %d
", age);
}
```

Para input robusto, leer una línea y parsearla explícitamente suele ser más fácil de validar que un formato `scanf` complejo. Comprueba siempre los retornos y usa length modifiers correctos para `size_t` y enteros fixed-width.
