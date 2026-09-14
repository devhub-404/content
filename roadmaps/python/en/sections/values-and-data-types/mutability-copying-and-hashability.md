# Mutability, Copying, and Hashability

Immutable built-ins include numbers, strings, bytes, and tuples whose contained values may still be mutable. Lists, dictionaries, sets, and most custom instances are mutable. Hashable objects need a stable hash/equality contract and can serve as dictionary keys or set elements.

```python
import copy

original = [[1, 2], [3, 4]]
shallow = original.copy()
deep = copy.deepcopy(original)
```

A shallow copy creates a new outer container but shares nested objects; a deep copy recursively duplicates supported content. Deep copying arbitrary object graphs is rarely a substitute for clear ownership and immutable data design.
