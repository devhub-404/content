# Names, Objects, and Assignment

Python variables are names bound to objects; assignment does not copy an object by default. Two names can refer to the same mutable object, so a mutation through one alias is visible through the other. Function arguments follow the same object-reference binding model.

```python
items = [1, 2, 3]
alias = items
alias.append(4)

print(items)  # [1, 2, 3, 4]
```

Reason about identity, mutability, and ownership conventions instead of treating variables as boxes that always contain independent values. Copy only when independent state is required, and know whether a copy is shallow or deep.
