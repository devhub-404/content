# Inheritance, `super`, and the MRO

Python supports multiple inheritance and resolves attribute/method lookup through the method resolution order (MRO). Cooperative multiple inheritance uses `super()` so each class can delegate to the next implementation in the MRO rather than naming one parent directly.

```python
class LoggingMixin:
    def save(self):
        print("saving")
        return super().save()

class Repository(LoggingMixin, BaseRepository):
    pass
```

Multiple inheritance is powerful for carefully designed mixins but can become difficult when classes maintain overlapping state or incompatible constructor expectations. Favor composition when relationships are not genuine substitutable type relationships.
