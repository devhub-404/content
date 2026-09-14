# Mutexes, Locks, and Condition Variables

Mutexes protect shared state by establishing mutual exclusion and synchronization. RAII lock wrappers such as `lock_guard`, `unique_lock`, and `scoped_lock` ensure unlocking happens on every scope exit. Condition variables let threads sleep until a state predicate may have changed.

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

Always wait with a predicate because wakeups can be spurious and the condition can change before the awakened thread acquires the mutex. Define a consistent lock order when several mutexes may be held to reduce deadlock risk.
