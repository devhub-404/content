# Lambdas and Callable Values

Functions and other callable objects are first-class values. A lambda creates a small anonymous function limited to one expression, while named `def` functions support statements, annotations, documentation, and clearer tracebacks.

```python
key = lambda user: user.name.casefold()
users.sort(key=key)

def apply(value, fn):
    return fn(value)
```

Use lambdas for short local callbacks where a name adds little. Promote nontrivial behavior to a named function so stack traces, tests, reuse, and documentation have a stable identity.
