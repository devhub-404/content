# Mutability, Copias y Hashability

Los built-ins inmutables incluyen numbers, strings, bytes y tuples cuyos contents aún pueden ser mutables. Lists, dicts, sets y la mayoría de custom objects son mutables. Los hashable objects necesitan hash/equality estables.

```python
import copy

original = [[1, 2], [3, 4]]
shallow = original.copy()
deep = copy.deepcopy(original)
```

Una shallow copy crea un outer container nuevo pero comparte nested objects; deep copy duplica recursivamente. Deep copy no sustituye ownership claro.
