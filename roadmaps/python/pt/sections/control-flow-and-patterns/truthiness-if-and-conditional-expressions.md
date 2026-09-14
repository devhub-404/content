# Truthiness, `if` e Conditional Expressions

Conditions usam truth-value testing: `False`, `None`, zero e containers vazios são false. Custom objects podem definir truth via `__bool__`/`__len__`. Conditional expression escolhe entre dois valores.

```python
label = "ready" if ready else "waiting"

if items:
    print("has items")
elif fallback is not None:
    print(fallback)
```

Use truthiness quando empty/zero/false realmente significam ausência. Use `is None` quando esses valores são válidos e distintos de missing.
