# Threads y Mutexes

La biblioteca C incluye una API de threads donde está soportada, con threads, mutexes, condition variables, thread-specific storage y call-once. Un mutex establece sincronización sobre estado compartido cuando todos siguen el mismo protocolo de locking.

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

No todas las implementaciones ofrecen todas las facilities opcionales, así que comprueba el baseline. Diseña ownership y orden de locks antes de añadir concurrencia: los data races son undefined behavior y deadlocks o lifetime races siguen siendo bugs lógicos.
