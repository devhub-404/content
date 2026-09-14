# Herencia, `super` y MRO

Python soporta herencia múltiple y resuelve lookup mediante method resolution order. La herencia múltiple cooperativa usa `super()` para delegar a la siguiente implementación del MRO.

```python
class LoggingMixin:
    def save(self):
        print("saving")
        return super().save()

class Repository(LoggingMixin, BaseRepository):
    pass
```

Es útil en mixins bien diseñados, pero difícil con estado/constructors conflictivos. Prefiere composición cuando no haya una relación real de subtype.
