# Benchmarking y Profiling

El trabajo de performance debe usar builds optimizados y medición. El harness estándar no ofrece un framework estable completo de benchmarking para todos los casos, por lo que los proyectos usan herramientas del ecosistema y profilers nativos.

```rust
pub fn process(values: &[u64]) -> u64 {
    values.iter().copied().sum()
}
```

Perfila antes de sustituir abstracciones safe por unsafe/manual tricks. Iterators, enums, generics y RAII suelen optimizar muy bien. Los costes reales dependen de allocations, cache, syscalls, locks, code size y compile time.
