# Argumentos Positional, Keyword y Variadic

Python puede exigir positional-only con `/`, keyword-only con `*`, y recoger extras en `*args`/`**kwargs`. Estos recursos hacen que la calling convention forme parte de la API.

```python
def request(url, /, method="GET", *, timeout=5, **headers):
    ...

request("/users", timeout=2, Accept="application/json")
```

Usa keyword-only para options y positional-only cuando el nombre del parameter no deba convertirse en contrato. Evita `**kwargs` arbitrario sin documentar keys.
