# Structural Pattern Matching

`match` compares a subject against structural patterns that can destructure sequences, mappings, classes, literals, alternatives, guards, and captures. It is closer to algebraic pattern matching than to a simple switch statement.

```python
match message:
    case {"type": "user", "id": int(user_id)}:
        handle_user(user_id)
    case ["move", x, y]:
        move(x, y)
    case _:
        ignore()
```

Use matching when the data shape itself drives behavior, especially parsers, protocol messages, and closed-ish domain states. Avoid extremely broad capture patterns that silently match more than intended.
