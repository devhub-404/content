# Truthiness, `if`, and Conditional Expressions

Conditions use truth-value testing: false values include `False`, `None`, numeric zero, and empty standard containers. Custom objects can define truth behavior through `__bool__` or `__len__`. The conditional expression chooses one of two values.

```python
label = "ready" if ready else "waiting"

if items:
    print("has items")
elif fallback is not None:
    print(fallback)
```

Use truthiness when empty/zero/false genuinely mean absence in the domain. Use explicit `is None` checks when `0`, `False`, or an empty container are valid distinct values that must not be confused with missing data.
