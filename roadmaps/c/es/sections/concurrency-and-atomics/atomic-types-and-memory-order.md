# Tipos Atómicos y Memory Ordering

Los tipos atómicos ofrecen operaciones que participan en el memory model de concurrencia sin data races sobre esos objetos. Las operaciones pueden usar distintos memory orders, desde relaxed hasta acquire/release y sequential consistency.

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

`memory_order_relaxed` garantiza atomicidad, no sincronización de datos relacionados. Los algoritmos lock-free requieren un diseño preciso de happens-before. Prefiere mutexes hasta que una necesidad medida y un protocolo demostrado justifiquen ordering de bajo nivel.
