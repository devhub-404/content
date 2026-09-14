# Benchmarking and Profiling

Performance work should use optimized builds and measurement. The stable standard test harness does not provide a complete stable benchmarking framework for every use case, so projects commonly use ecosystem benchmark tools while native profilers measure CPU, allocations, cache behavior, and system activity.

```rust
pub fn process(values: &[u64]) -> u64 {
    values.iter().copied().sum()
}
```

Profile before replacing safe abstractions with unsafe or manual memory tricks. Iterator chains, enums, generics, and RAII often optimize very well. The meaningful costs are workload-specific: allocation patterns, cache locality, syscalls, lock contention, code size, and compile time all matter differently.
