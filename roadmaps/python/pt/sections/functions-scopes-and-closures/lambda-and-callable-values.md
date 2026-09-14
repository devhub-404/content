# Lambdas e Valores Callable

Functions e outros callables são first-class values. Lambda cria anonymous function de uma expressão, enquanto `def` suporta statements, annotations e docs.

```python
key = lambda user: user.name.casefold()
users.sort(key=key)

def apply(value, fn):
    return fn(value)
```

Use lambda para callbacks curtos. Promova comportamento não trivial para função nomeada para melhorar stack traces, testes e documentação. Prefira uma função nomeada quando a lógica cresce ou precisa de documentação, testes e traceback mais claros.
