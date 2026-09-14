# The Iterable and Iterator Protocol

An iterable produces an iterator through `iter()`, and an iterator yields successive values through `next()` until it raises `StopIteration`. `for`, comprehensions, unpacking, `sum`, `list`, and many standard APIs consume this protocol.

```python
iterator = iter(values)
while True:
    try:
        value = next(iterator)
    except StopIteration:
        break
    print(value)
```

Iterators are stateful and usually single-pass. An iterable such as a list can produce a fresh iterator many times. When designing custom types, implement iteration only if sequential traversal is a natural part of the object contract.
