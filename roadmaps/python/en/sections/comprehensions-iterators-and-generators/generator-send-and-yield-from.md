# Generator Delegation and `yield from`

`yield from` delegates iteration to another iterable and, for generators, also participates in the extended send/throw/return protocol. It removes boilerplate when one generator composes another sequence directly.

```python
def chain(*iterables):
    for iterable in iterables:
        yield from iterable
```

Most application generators only need ordinary yielding and delegation. The full coroutine-like generator protocol is powerful but can be harder to reason about than `async`/`await` for asynchronous workflows.
