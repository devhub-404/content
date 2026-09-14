# Structural Pattern Matching

`match` compara subject com structural patterns que destructure sequences, mappings, classes, literals, alternatives, guards e captures. É mais próximo de pattern matching algébrico que de switch simples.

```python
match message:
    case {"type": "user", "id": int(user_id)}:
        handle_user(user_id)
    case ["move", x, y]:
        move(x, y)
    case _:
        ignore()
```

Use quando o shape dos dados dirige comportamento, como parsers/protocols. Evite capture patterns amplos que matcham mais do que o esperado.
