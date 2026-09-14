# Lists, Tuples e Sequences

Lists são sequences ordenadas mutáveis e tuples containers imutáveis usados em groupings fixos/retornos. Ambos suportam indexing, slicing, iteration, membership e unpacking.

```python
values = [10, 20, 30]
values.append(40)

point = (3, 4)
x, y = point
```

Use list para coleção mutável e tuple para grouping pequeno e fixo. Se fields precisam nomes/comportamento, dataclass ou class comunica melhor.
