# Debugging, Profiling y Diagnostics

El tooling .NET inspecciona breakpoints, threads, tasks, exceptions, memoria, GC, CPU, allocations, events, dumps y distributed traces. Los problemas de performance en release necesitan profiler, no suposiciones desde el source.

```csharp
using var activity = new Activity("process-order");
activity.Start();

ProcessOrder(order);

activity.Stop();
```

Reproduce con el caso mínimo fiable, encuentra el primer punto donde el estado real diverge del esperado y usa la herramienta adecuada. Logging, tracing, metrics, dumps y profilers responden preguntas distintas.
