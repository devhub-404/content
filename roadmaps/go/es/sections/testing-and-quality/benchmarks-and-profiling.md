# Benchmarks y Profiling

El package testing soporta benchmarks y Go actual ofrece loop facilities para medir trabajo repetido. Los benchmarks deben aislar la operación, controlar setup y usar condiciones suficientemente representativas.

```go
func BenchmarkParse(b *testing.B) {
    input := []byte("example")

    for b.Loop() {
        Parse(input)
    }
}
```

Usa `pprof` y perfiles runtime para encontrar bottlenecks reales de CPU, allocations, blocking, mutex y goroutines. Optimiza hot paths medidos. Escape/inlining pueden cambiar entre versiones, así que las assumptions necesitan evidencia.
