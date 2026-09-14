# Type Annotations and Static Checkers

Type annotations attach metadata describing intended types, and static checkers such as mypy, pyright, or IDE analyzers use that information without changing ordinary Python runtime enforcement. Python 3.14 also changes how annotations are evaluated at runtime, making introspection tools use newer annotation APIs.

```python
def greet(name: str) -> str:
    return f"Hello, {name}"

count: int = 0
```

Annotate public boundaries, complex data shapes, and reusable libraries first. Avoid turning every trivial local into annotation noise. Runtime validation remains separate because external data can violate a static annotation.
