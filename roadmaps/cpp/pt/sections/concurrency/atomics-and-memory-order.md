# Atômicos e Memory Ordering

Objetos atômicos suportam operações race-free e participam do memory model. Ordering vai de relaxed até acquire/release e sequential consistency.

```cpp
std::atomic<unsigned> counter{0};

counter.fetch_add(
    1,
    std::memory_order_relaxed
);
```

Relaxed não sincroniza dados relacionados. Correção lock-free depende de happens-before preciso e erros podem sobreviver testes. Prefira mutexes até haver necessidade medida e protocolo bem revisado.
