# Benchmarks e Profiling

Package testing suporta benchmarks e Go atual fornece loop facilities para medir trabalho repetido. Benchmarks devem isolar operação, controlar setup e usar condições representativas.

```go
func BenchmarkParse(b *testing.B) {
    input := []byte("example")

    for b.Loop() {
        Parse(input)
    }
}
```

Use `pprof` e profiles de runtime para encontrar CPU, allocations, blocking, mutex e goroutine bottlenecks reais. Otimize hot paths medidos. Escape/inlining podem mudar entre versões, então assumptions precisam de evidência.
