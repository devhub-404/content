# Scope, `global`, `nonlocal` y Closures

La resolución de nombres sigue local, enclosing, global y built-in. Una closure conserva acceso a bindings externos. `nonlocal` rebindea una variable enclosing y `global` una variable de module.

```python
def make_counter():
    count = 0

    def next_value():
        nonlocal count
        count += 1
        return count

    return next_value
```

Prefiere retornar state o usar objetos frente a muchas functions mutando globals. Las closures sirven para estado pequeño, pero mutation escondida en scopes profundos dificulta tests.
