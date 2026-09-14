# Threads and Mutexes

The C standard library includes a thread API where supported, with threads, mutexes, condition variables, thread-specific storage, and call-once facilities. A mutex establishes synchronization around shared mutable state when all participants follow the same locking protocol.

```c
#include <threads.h>

mtx_t lock;

int worker(void *arg) {
    mtx_lock(&lock);
    /* protected shared state */
    mtx_unlock(&lock);
    return 0;
}
```

Not every implementation provides every optional concurrency facility, so check your platform baseline. Design ownership and lock ordering before adding threads: data races are undefined behavior, and deadlocks or lifetime races are still logic bugs even when every individual library call succeeds.
