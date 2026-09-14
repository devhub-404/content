# Diccionarios y Sets

Un `dict` mapea hashable keys a values y preserva insertion order. Un `set` almacena valores únicos y soporta operaciones de conjunto. Ambos dependen de hashing/equality estables.

```python
counts = {"ready": 2, "failed": 1}
counts["ready"] += 1

seen = {"python", "typing"}
seen.add("asyncio")
```

Usa dict para lookup y set para unicidad/membership. Prefiere `get`, `defaultdict` o `Counter` cuando expresen directamente la operación.
