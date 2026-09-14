# Generators y `yield`

Una function con `yield` retorna un generator iterator. El estado local se suspende entre values y continúa cuando el consumer pide el siguiente item, útil para streaming y traversal.

```python
def even_numbers(limit):
    for value in range(0, limit + 1, 2):
        yield value

for value in even_numbers(10):
    print(value)
```

El código corre lazy, así que exceptions/I/O pueden ocurrir durante iteration. Garantiza que los recursos sigan válidos o usa un context manager para el lifecycle.
