# Conversiones y Promociones Enteras

C realiza muchas conversiones implícitas. Los tipos enteros pequeños suelen sufrir integer promotions antes de la aritmética, y las expresiones que mezclan signed, unsigned, enteros y floating siguen las usual arithmetic conversions. Una conversión puede cambiar el valor cuando el destino no representa el origen.

```c
#include <stdint.h>

uint8_t a = 250;
uint8_t b = 10;

int sum = a + b;   /* promoted before addition */
```

No razones solo por el tipo declarado: los operandos pueden promocionarse antes de ejecutar el operador. Activa warnings y usa conversiones explícitas comprobadas en fronteras donde truncamiento o cambio de signo sería un bug.
