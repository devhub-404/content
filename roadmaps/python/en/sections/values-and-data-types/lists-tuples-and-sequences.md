# Lists, Tuples, and Sequences

Lists are mutable ordered sequences, while tuples are immutable sequence containers often used for fixed-position records or return values. Both support indexing, slicing, iteration, membership, and unpacking, but their mutation and hashability properties differ.

```python
values = [10, 20, 30]
values.append(40)

point = (3, 4)
x, y = point
```

Use a list for a changing collection and a tuple for a small fixed grouping where position is meaningful. If fields need names or behavior, a dataclass, named tuple, or ordinary class usually communicates the shape better.
