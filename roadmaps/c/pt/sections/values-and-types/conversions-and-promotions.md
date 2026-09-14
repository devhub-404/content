# Conversões e Promoções Inteiras

C realiza muitas conversões implícitas. Tipos inteiros pequenos normalmente sofrem integer promotions antes da aritmética, e expressões misturando signed, unsigned, inteiros e floating seguem as usual arithmetic conversions. Uma conversão pode mudar o valor quando o destino não representa a origem.

```c
#include <stdint.h>

uint8_t a = 250;
uint8_t b = 10;

int sum = a + b;   /* promoted before addition */
```

Não raciocine apenas pelo tipo declarado: os operandos podem ser promovidos antes do operador. Habilite warnings em código sensível e use conversões explícitas verificadas nas fronteiras onde truncamento ou mudança de sinal seria bug.
