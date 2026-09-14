# Lambdas y Valores Callable

Las functions y otros callables son first-class values. Una lambda crea una anonymous function de una expresión, mientras `def` soporta statements, annotations y docs.

```python
key = lambda user: user.name.casefold()
users.sort(key=key)

def apply(value, fn):
    return fn(value)
```

Usa lambda para callbacks cortos. Promueve comportamiento no trivial a una función nombrada para mejorar stack traces, tests y documentación.
