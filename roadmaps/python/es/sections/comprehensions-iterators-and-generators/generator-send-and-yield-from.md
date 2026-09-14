# Delegación de Generator y `yield from`

`yield from` delega iteration a otro iterable y también participa en el protocol extendido de generators. Elimina boilerplate al componer secuencias.

```python
def chain(*iterables):
    for iterable in iterables:
        yield from iterable
```

La mayoría de generators solo necesita yield/delegation normales. El protocol completo es potente, pero async/await es más claro para workflows asíncronos.
