# Benchmarking e Profiling

Performance deve usar builds optimized e medição. O harness standard não fornece framework stable completo para benchmark em todo caso, então projetos usam ferramentas do ecossistema e profilers nativos.

```rust
pub fn process(values: &[u64]) -> u64 {
    values.iter().copied().sum()
}
```

Profile antes de trocar abstrações safe por unsafe/manual tricks. Iterators, enums, generics e RAII frequentemente otimizam bem. Custos reais dependem de allocations, cache, syscalls, locks, code size e compile time.
