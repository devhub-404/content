# Structural Pattern Matching

`match` compara un subject con structural patterns que destructure sequences, mappings, classes, literals, alternatives, guards y captures. Se parece más a pattern matching algebraico que a un switch simple.

```python
match message:
    case {"type": "user", "id": int(user_id)}:
        handle_user(user_id)
    case ["move", x, y]:
        move(x, y)
    case _:
        ignore()
```

Úsalo cuando el shape de los datos dirija el comportamiento, como parsers/protocols. Evita capture patterns amplios que hagan match con más de lo esperado.
