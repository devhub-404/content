# Delegação de Generator e `yield from`

`yield from` delega iteration a outro iterable e também participa do protocol estendido de generators. Remove boilerplate ao compor sequências.

```python
def chain(*iterables):
    for iterable in iterables:
        yield from iterable
```

A maioria dos generators só precisa yield/delegation comuns. O protocol completo é poderoso, mas async/await é mais claro para workflows assíncronos.
