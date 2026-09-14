# Atomics and Memory Ordering

Atomic objects support race-free atomic operations and participate in the C++ memory model. Memory ordering ranges from relaxed atomicity through acquire/release relationships to sequential consistency.

```cpp
std::atomic<unsigned> counter{0};

counter.fetch_add(
    1,
    std::memory_order_relaxed
);
```

A relaxed atomic does not synchronize unrelated data. Lock-free correctness depends on precise happens-before reasoning, and mistakes can survive testing for a long time. Prefer mutexes unless measurements and a well-reviewed concurrency protocol justify atomics.
