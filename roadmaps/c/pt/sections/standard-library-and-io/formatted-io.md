# I/O Formatado

Funções `printf` formatam valores segundo uma format string e a família `scanf` faz parsing para endereços fornecidos pelo caller. Os specifiers precisam corresponder aos tipos reais; mismatch em I/O variádico pode gerar undefined behavior.

```c
#include <stdio.h>

int age = 0;
if (scanf("%d", &age) == 1) {
    printf("age = %d
", age);
}
```

Para input robusto, ler uma linha e fazer parsing explícito costuma ser mais fácil de validar que formatos `scanf` complexos. Sempre cheque retornos e use length modifiers corretos para tipos como `size_t` e inteiros fixed-width.
