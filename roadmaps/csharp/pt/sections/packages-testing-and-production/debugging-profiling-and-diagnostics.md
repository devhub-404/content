# Debugging, Profiling e Diagnostics

Tooling .NET inspeciona breakpoints, threads, tasks, exceptions, memory, GC, CPU, allocations, events, dumps e distributed traces. Problemas de performance em release precisam profiler, não guesses pelo source.

```csharp
using var activity = new Activity("process-order");
activity.Start();

ProcessOrder(order);

activity.Stop();
```

Reproduza com caso mínimo confiável, encontre o primeiro ponto onde estado real diverge do esperado e use a ferramenta adequada. Logging, tracing, metrics, dumps e profilers respondem perguntas diferentes.
