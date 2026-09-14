# Decorators

Decorator transforma ou registra function/class/method na definition. A syntax equivale a reassign do objeto por chamadas de decorator e sustenta routing, caching, validation e frameworks.

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

Ao envolver functions, use `functools.wraps` para preservar metadata. Decorators escondem control flow, então mantenha-os focados e evite stacks excessivos.
