# Mutexes, Locks y Condition Variables

Los mutexes protegen estado compartido y establecen sincronización. Wrappers RAII como `lock_guard`, `unique_lock` y `scoped_lock` garantizan unlock en toda salida de scope. Las condition variables permiten esperar hasta que un predicado pueda haber cambiado.

```cpp
std::mutex mutex;
std::condition_variable cv;
bool ready = false;

{
    std::lock_guard lock(mutex);
    ready = true;
}
cv.notify_one();
```

Espera siempre con predicate por los spurious wakeups y porque el estado puede cambiar antes de recuperar el mutex. Define un orden consistente cuando puedan mantenerse varios mutexes para reducir deadlocks.
