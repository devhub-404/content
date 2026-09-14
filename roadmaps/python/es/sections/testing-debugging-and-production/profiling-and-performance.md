# Profiling y Performance

La performance en Python empieza con medición. `cProfile`, sampling profilers y allocation tools responden preguntas distintas; algoritmo/data shape suelen importar más que micro-optimizar sintaxis.

```python
import cProfile

cProfile.run("main()", "profile.stats")
```

Usa built-ins y native libraries cuando encajen. No supongas que comprehension/generator/loop es más rápido sin medir workload/interpreter real.
