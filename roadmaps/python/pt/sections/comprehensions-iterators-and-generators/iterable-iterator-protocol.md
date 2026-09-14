# Protocolos Iterable e Iterator

Iterable produz iterator por `iter()` e iterator retorna values por `next()` até `StopIteration`. `for`, comprehensions, unpacking e várias APIs usam esse protocolo.

```python
iterator = iter(values)
while True:
    try:
        value = next(iterator)
    except StopIteration:
        break
    print(value)
```

Iterators são stateful e normalmente single-pass; iterable como list produz novos iterators. Implemente custom iteration quando traversal é natural ao tipo.
