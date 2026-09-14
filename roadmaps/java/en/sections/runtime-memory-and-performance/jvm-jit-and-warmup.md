# JIT Compilation and Warmup

The JVM can interpret and JIT-compile hot code using runtime profiling information. Inlining, escape analysis, devirtualization, and other optimizations mean performance can change after warmup and differ from simple source-level expectations.

```java
static long work(int value) {
    return (long) value * value;
}
```

Use a proper benchmark harness such as JMH for microbenchmarks because dead-code elimination, warmup, constant folding, GC, and CPU effects easily invalidate naive timing loops. Profile full applications as well; microbenchmarks answer only narrow questions.
