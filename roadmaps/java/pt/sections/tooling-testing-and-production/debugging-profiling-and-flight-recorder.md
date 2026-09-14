# Debugging, Profiling e Flight Recorder

JDK inclui ferramentas para thread dumps, heap, process commands, monitoring e Java Flight Recorder. Debuggers de IDE adicionam breakpoints/watches e profilers revelam CPU/allocations.

```java
// Useful JVM diagnostics include:
// jcmd
// jstack
// jmap
// jfr
// jconsole
```

Use a ferramenta certa: thread dump para deadlock/stall, heap para retention, JFR para eventos production-friendly e CPU profiler para hot methods. Logging sozinho raramente basta.
