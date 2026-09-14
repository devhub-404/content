# Atomic Types and Memory Ordering

Atomic types provide operations that participate in C's concurrency memory model without data races on those atomic objects. Operations can use different memory-order constraints, from relaxed atomicity to acquire/release and sequentially consistent ordering.

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

`memory_order_relaxed` guarantees atomic modification but not synchronization of unrelated data. Correct lock-free algorithms require a precise happens-before design; using a weaker order because it looks faster can silently break the program. Prefer mutexes until a measured need and a proven atomic protocol justify lower-level ordering.
