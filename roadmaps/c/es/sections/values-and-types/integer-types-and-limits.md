# Tipos Enteros y Límites

C ofrece varios tipos enteros signed y unsigned cuyas anchuras exactas dependen de la implementación dentro de unos rangos mínimos. `<stdint.h>` añade tipos de anchura fija como `int32_t` cuando están disponibles, además de familias least-width, fast y pointer-sized.

```c
#include <stdint.h>
#include <inttypes.h>

int32_t temperature = -12;
uint64_t count = 1000;

printf("%" PRIu64 "
", count);
```

Elige el tipo por el rango y la interfaz que necesitas, no suponiendo que `int` siempre tenga 32 bits o `long` 64. `<limits.h>`, `<stdint.h>` y `<inttypes.h>` proporcionan límites y formatos portables. La aritmética unsigned hace wrap módulo su rango; el overflow signed es undefined.
