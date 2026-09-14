# Mutability, Cópias e Hashability

Built-ins imutáveis incluem numbers, strings, bytes e tuples cujos contents ainda podem ser mutáveis. Lists, dicts, sets e a maioria de custom objects são mutáveis. Hashable objects precisam hash/equality estáveis.

```python
import copy

original = [[1, 2], [3, 4]]
shallow = original.copy()
deep = copy.deepcopy(original)
```

Shallow copy cria outer container novo mas compartilha nested objects; deep copy duplica recursivamente. Deep copy não substitui ownership claro.
