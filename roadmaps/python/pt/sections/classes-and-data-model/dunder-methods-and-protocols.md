# Dunder Methods e Protocols

Special methods conectam custom objects à syntax e built-in protocols: `__len__`, `__iter__`, context managers, operators, comparisons, formatting e attribute hooks.

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

Implemente protocol apenas quando o tipo realmente possui aquele significado. Operator overloads surpreendentes ou sequence behavior fake dificultam código. Em APIs públicas, escolha o recurso que comunica melhor o contrato em vez de depender apenas de conveniência sintática.
