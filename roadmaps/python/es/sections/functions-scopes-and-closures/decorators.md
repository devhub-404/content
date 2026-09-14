# Decorators

Un decorator transforma o registra una function/class/method al definirla. La sintaxis equivale a reasignar el objeto mediante llamadas de decorator y sustenta routing, caching, validación y frameworks.

```python
def trace(fn):
    def wrapper(*args, **kwargs):
        print(fn.__name__)
        return fn(*args, **kwargs)
    return wrapper

@trace
def work():
    pass
```

Al envolver functions, usa `functools.wraps` para conservar metadata. Los decorators esconden control flow, así que mantenlos enfocados y evita stacks excesivos.
