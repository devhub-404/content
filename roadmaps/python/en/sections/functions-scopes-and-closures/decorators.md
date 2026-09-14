# Decorators

A decorator transforms or registers a function, class, or method at definition time. Decorator syntax is equivalent to reassigning the defined object through one or more decorator calls, which powers routing, caching, validation, registration, and framework metadata.

```python
def trace(fn):
    def wrapper(*args, **kwargs):
        print(fn.__name__)
        return fn(*args, **kwargs)
    return wrapper

@trace
def work():
    pass
```

When wrapping functions, use `functools.wraps` to preserve important metadata. Decorators can hide control flow, so keep them focused and avoid stacking many behavior-changing layers whose order becomes difficult to understand.
