# `for`, `while`, `break` y `else` de Loop

`for` consume un iterable en vez de un header estilo C y `while` repite por condición. `break` sale, `continue` avanza y el `else` del loop corre solo si no hubo `break`.

```python
for item in items:
    if matches(item):
        found = item
        break
else:
    found = None
```

Loop `else` sirve para búsquedas, pero puede sorprender. Úsalo cuando elimine un flag con claridad o prefiere helper/`next` si expresa mejor.
