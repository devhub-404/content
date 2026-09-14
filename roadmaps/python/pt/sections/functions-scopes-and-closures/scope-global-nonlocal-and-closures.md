# Escopo, `global`, `nonlocal` e Closures

Name lookup segue local, enclosing, global e built-in. Closure mantém acesso a bindings externos. `nonlocal` rebinda variável enclosing e `global` variável de module.

```python
def make_counter():
    count = 0

    def next_value():
        nonlocal count
        count += 1
        return count

    return next_value
```

Prefira retornar state ou usar objects em vez de muitas funções mutando globals. Closures servem a estado pequeno, mas mutation escondida em scopes profundos dificulta testes.
