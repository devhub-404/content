# Debugging, Profiling y Flight Recorder

El JDK incluye herramientas para thread dumps, heap, process commands, monitoring y Java Flight Recorder. Los debuggers de IDE añaden breakpoints/watches y los profilers revelan CPU/allocations.

```java
// Useful JVM diagnostics include:
// jcmd
// jstack
// jmap
// jfr
// jconsole
```

Usa la herramienta correcta: thread dump para deadlock/stall, heap para retention, JFR para eventos production-friendly y CPU profiler para hot methods. El logging por sí solo rara vez basta.
