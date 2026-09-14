# Exceptions Customizadas

Custom exception classes dão categoria estável para caller capturar sem parsear texto. Domain exceptions podem herdar de built-ins semânticos como `ValueError` ou de `Exception`.

```python
class InvalidOrderError(ValueError):
    pass

if total < 0:
    raise InvalidOrderError("total cannot be negative")
```

Mantenha hierarquia pequena e útil. Inclua contexto acionável, mas não exponha secrets ou payloads grandes em logs por default.
