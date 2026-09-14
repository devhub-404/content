# Profiling and Performance

Python performance work starts with measurement. `cProfile`, sampling profilers, allocation tools, and line-level profilers answer different questions, while algorithm choice and data representation usually matter more than micro-optimizing syntax.

```python
import cProfile

cProfile.run("main()", "profile.stats")
```

Use built-ins and vectorized/native libraries where they fit, because much work can run in optimized C/Rust code. Avoid assuming a comprehension, generator, or loop is faster without measuring the actual workload and interpreter version.
