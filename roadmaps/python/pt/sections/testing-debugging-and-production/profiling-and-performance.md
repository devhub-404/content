# Profiling e Performance

Performance Python começa com medição. `cProfile`, sampling profilers e allocation tools respondem perguntas diferentes; algoritmo/data shape normalmente importam mais que micro-otimizar syntax.

```python
import cProfile

cProfile.run("main()", "profile.stats")
```

Use built-ins e native libraries quando cabem. Não presuma que comprehension/generator/loop é mais rápido sem medir workload/interpreter real.
