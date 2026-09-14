# Threads e Mutexes

A biblioteca C inclui API de threads onde suportada, com threads, mutexes, condition variables, thread-specific storage e call-once. Um mutex estabelece sincronização sobre estado compartilhado quando todos seguem o mesmo protocolo de lock.

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

Nem toda implementação fornece todas as facilities opcionais, então verifique o baseline da plataforma. Projete ownership e ordem de locks antes de adicionar concorrência: data races são undefined behavior e deadlocks ou lifetime races continuam bugs lógicos.
