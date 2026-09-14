# Exceptions Personalizadas

Las custom exception classes dan una categoría estable para que el caller capture sin parsear texto. Las domain exceptions pueden heredar de built-ins semánticos como `ValueError` o de `Exception`.

```python
class InvalidOrderError(ValueError):
    pass

if total < 0:
    raise InvalidOrderError("total cannot be negative")
```

Mantén la jerarquía pequeña y útil. Incluye contexto accionable, pero no expongas secrets o payloads grandes en logs por defecto.
