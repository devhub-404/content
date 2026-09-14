# Atómicos y Memory Ordering

Los objetos atómicos soportan operaciones race-free y participan en el memory model. El ordering va desde relaxed hasta acquire/release y sequential consistency.

```cpp
std::atomic<unsigned> counter{0};

counter.fetch_add(
    1,
    std::memory_order_relaxed
);
```

Relaxed no sincroniza datos relacionados. La corrección lock-free depende de un happens-before preciso y los errores pueden sobrevivir mucho tiempo a los tests. Prefiere mutexes salvo necesidad medida y protocolo bien revisado.
