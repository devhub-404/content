# Dunder Methods and Protocols

Special methods such as `__len__`, `__iter__`, `__enter__`, arithmetic operators, comparisons, formatting, and attribute hooks connect custom objects to Python syntax and built-in protocols. This protocol-driven data model is one of Python’s defining features.

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

Implement a protocol only when your type genuinely has that meaning. Surprising operator overloads or fake sequence behavior make code harder to understand. Prefer standard protocol expectations so generic Python code works naturally with your type.
