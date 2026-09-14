# Debugging, Profiling, and Flight Recorder

The JDK includes diagnostic tools for thread dumps, heap information, process commands, monitoring, and Java Flight Recorder. IDE debuggers add breakpoints, watches, exception stops, and thread inspection, while profilers reveal CPU and allocation hot spots.

```java
// Useful JVM diagnostics include:
// jcmd
// jstack
// jmap
// jfr
// jconsole
```

Use the tool that matches the symptom: thread dumps for deadlocks/stalls, heap analysis for retention, JFR for low-overhead production events, and CPU profiling for hot methods. Logging alone is rarely enough for runtime performance diagnosis.
