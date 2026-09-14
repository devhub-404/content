# Comportamento Undefined, Unspecified e Implementation-defined

O padrão C deixa deliberadamente alguns comportamentos undefined, unspecified ou implementation-defined. Undefined behavior não impõe requisitos após a operação inválida, então o compilador pode otimizar assumindo que ela nunca ocorre. Overflow de inteiro signed, dereference de ponteiro inválido e muitos acessos fora de bounds são exemplos importantes.

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

Comportamento implementation-defined deve ser documentado pela implementação, enquanto unspecified permite um entre vários resultados válidos sem exigir qual foi escolhido. C portável evita depender de UB e isola hipóteses de plataforma em interfaces verificadas ou configuração.
