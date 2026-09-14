# Protocolos Iterable e Iterator

Un iterable produce un iterator mediante `iter()` y el iterator entrega values con `next()` hasta `StopIteration`. `for`, comprehensions, unpacking y muchas APIs usan este protocolo.

```python
iterator = iter(values)
while True:
    try:
        value = next(iterator)
    except StopIteration:
        break
    print(value)
```

Los iterators son stateful y normalmente single-pass; un iterable como list produce nuevos iterators. Implementa custom iteration cuando el traversal sea natural al tipo.
