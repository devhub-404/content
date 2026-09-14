# Dictionaries e Sets

`dict` mapeia hashable keys para values e preserva insertion order. `set` armazena valores únicos e suporta operações de conjunto. Ambos dependem de hashing/equality estáveis.

```python
counts = {"ready": 2, "failed": 1}
counts["ready"] += 1

seen = {"python", "typing"}
seen.add("asyncio")
```

Use dict para lookup e set para unicidade/membership. Prefira `get`, `defaultdict` ou `Counter` quando expressam diretamente a operação.
