# Dunder Methods y Protocols

Los special methods conectan custom objects con la sintaxis y built-in protocols: `__len__`, `__iter__`, context managers, operators, comparisons, formatting y attribute hooks.

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __len__(self):
        return 2

    def __repr__(self):
        return f"Point({self.x!r}, {self.y!r})"
```

Implementa un protocol solo cuando el tipo tenga realmente ese significado. Operator overloads sorprendentes o sequence behavior falso dificultan el código.
