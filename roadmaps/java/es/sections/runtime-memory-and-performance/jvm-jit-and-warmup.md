# JIT Compilation y Warmup

La JVM puede interpretar y JIT-compile hot code usando profiling runtime. Inlining, escape analysis y devirtualization hacen que la performance cambie tras warmup y difiera de intuiciones basadas en source.

```java
static long work(int value) {
    return (long) value * value;
}
```

Usa un harness como JMH para microbenchmarks porque warmup, dead-code elimination, constant folding y GC invalidan timers ingenuos. Perfila también aplicaciones completas.
