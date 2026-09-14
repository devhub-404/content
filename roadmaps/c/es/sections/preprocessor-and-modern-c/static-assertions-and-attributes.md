# Static Assertions y Attributes

`static_assert` comprueba una condición constante durante la traducción y sirve para assumptions de layout, configuración y plataforma. C23 también estandariza sintaxis de attributes para metadata como `[[nodiscard]]`, `[[deprecated]]` y `[[maybe_unused]]` según las reglas del lenguaje.

```c
#include <stdint.h>

static_assert(sizeof(uint32_t) == 4);

[[nodiscard]]
int write_record(const void *data, size_t size);
```

Usa assertions de compile time para hechos que el compilador puede demostrar. Los attributes deben comunicar intención real de API u optimización y las extensiones específicas de implementación requieren planificación de portabilidad.
