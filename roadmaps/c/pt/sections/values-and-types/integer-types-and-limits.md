# Tipos Inteiros e Limites

C fornece vários tipos inteiros signed e unsigned cujas larguras exatas dependem da implementação, dentro de ranges mínimos. `<stdint.h>` acrescenta tipos fixed-width como `int32_t` quando disponíveis, além de famílias least-width, fast e pointer-sized.

```c
#include <stdint.h>
#include <inttypes.h>

int32_t temperature = -12;
uint64_t count = 1000;

printf("%" PRIu64 "
", count);
```

Escolha o tipo pelo range e interface de que precisa, não assumindo que `int` sempre tem 32 bits ou `long` sempre 64. `<limits.h>`, `<stdint.h>` e `<inttypes.h>` fornecem limites e formatação portável. Aritmética unsigned faz wrap módulo o range; overflow signed é undefined.
