# Herança, `super` e MRO

Python suporta múltipla herança e resolve lookup pela method resolution order. Multiple inheritance cooperativa usa `super()` para delegar ao próximo implementation no MRO.

```python
class LoggingMixin:
    def save(self):
        print("saving")
        return super().save()

class Repository(LoggingMixin, BaseRepository):
    pass
```

É útil em mixins bem desenhados, mas difícil com estado/constructors conflitantes. Prefira composição quando não há relação real de subtype.
