# Debugging, Profiling, and Diagnostics

.NET tooling can inspect breakpoints, threads, tasks, exceptions, memory, GC activity, CPU samples, allocations, events, dumps, and distributed traces. Release-build performance problems often need profilers rather than source-level guesses.

```csharp
using var activity = new Activity("process-order");
activity.Start();

ProcessOrder(order);

activity.Stop();
```

Reproduce a problem with the smallest reliable case, identify the first point where observed state diverges from expected state, and use the diagnostic tool suited to that layer. Logging, tracing, metrics, dumps, and profilers answer different questions.
