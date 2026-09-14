# Benchmarks and Profiling

The testing package supports benchmarks, and current Go provides benchmark loop facilities for measuring repeated work. Benchmarks should isolate the operation of interest, control setup cost, and run under conditions representative enough to make comparisons meaningful.

```go
func BenchmarkParse(b *testing.B) {
    input := []byte("example")

    for b.Loop() {
        Parse(input)
    }
}
```

Use `pprof` and execution/runtime profiles to find actual CPU, allocation, blocking, mutex, and goroutine bottlenecks. Optimize measured hot paths, not code that merely looks low-level. Compiler escape and inlining decisions can change across versions, so performance assumptions need evidence.
