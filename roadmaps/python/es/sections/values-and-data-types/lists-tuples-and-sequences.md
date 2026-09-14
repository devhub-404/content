# Lists, Tuples y Sequences

Las lists son sequences ordenadas mutables y los tuples containers inmutables usados en agrupaciones fijas/retornos. Ambos soportan indexing, slicing, iteration, membership y unpacking.

```python
values = [10, 20, 30]
values.append(40)

point = (3, 4)
x, y = point
```

Usa list para colección mutable y tuple para agrupación pequeña y fija. Si los fields necesitan nombres/comportamiento, dataclass o class comunica mejor.
