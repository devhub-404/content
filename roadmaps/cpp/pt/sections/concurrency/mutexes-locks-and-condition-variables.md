# Mutexes, Locks e Condition Variables

Mutexes protegem estado compartilhado e estabelecem sincronização. Wrappers RAII como `lock_guard`, `unique_lock` e `scoped_lock` garantem unlock em toda saída de scope. Condition variables permitem esperar até que um predicado possa ter mudado.

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

Espere sempre com predicate por causa de spurious wakeups e races antes de readquirir o mutex. Defina ordem consistente quando múltiplos mutexes podem ser segurados para reduzir deadlocks.
