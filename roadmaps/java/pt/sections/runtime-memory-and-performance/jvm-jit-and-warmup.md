# JIT Compilation e Warmup

A JVM pode interpretar e JIT-compile hot code usando profiling runtime. Inlining, escape analysis e devirtualization fazem performance mudar após warmup e divergir de intuição pelo source.

```java
static long work(int value) {
    return (long) value * value;
}
```

Use harness como JMH para microbenchmarks porque warmup, dead-code elimination, constant folding e GC quebram timers ingênuos. Profile aplicações completas também.
