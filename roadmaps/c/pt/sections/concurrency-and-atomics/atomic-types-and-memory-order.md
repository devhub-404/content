# Tipos Atômicos e Memory Ordering

Tipos atômicos fornecem operações que participam do memory model de concorrência sem data race nesses objetos. Operações podem usar diferentes memory orders, de relaxed até acquire/release e sequential consistency.

```c
#include <stdatomic.h>

atomic_uint counter = 0;

void increment(void) {
    atomic_fetch_add_explicit(
        &counter,
        1,
        memory_order_relaxed
    );
}
```

`memory_order_relaxed` garante atomicidade, não sincronização de dados relacionados. Algoritmos lock-free exigem design preciso de happens-before. Prefira mutexes até que uma necessidade medida e um protocolo comprovado justifiquem ordering de baixo nível.
