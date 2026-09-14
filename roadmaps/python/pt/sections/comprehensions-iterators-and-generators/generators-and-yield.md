# Generators e `yield`

Function com `yield` retorna generator iterator. Estado local suspende entre values e retoma quando consumer pede próximo item, útil para streaming e traversal.

```python
def even_numbers(limit):
    for value in range(0, limit + 1, 2):
        yield value

for value in even_numbers(10):
    print(value)
```

Código roda lazy, então exceptions/I/O podem ocorrer durante iteration. Garanta que recursos permaneçam válidos ou use context manager para lifecycle.
