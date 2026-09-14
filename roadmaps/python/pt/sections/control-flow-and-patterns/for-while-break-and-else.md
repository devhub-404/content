# `for`, `while`, `break` e `else` de Loop

`for` consome iterable em vez de header C-style, e `while` repete por condição. `break` sai, `continue` avança e `else` do loop roda apenas sem `break`.

```python
for item in items:
    if matches(item):
        found = item
        break
else:
    found = None
```

Loop `else` serve bem a buscas, mas pode surpreender. Use quando remove flag de forma clara ou prefira helper/`next` se expressa melhor.
