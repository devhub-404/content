# Scope, `global`, `nonlocal`, and Closures

Name lookup follows local, enclosing, global, and built-in scopes. A closure can retain access to enclosing bindings after the outer function returns. `nonlocal` rebinds an enclosing function variable; `global` rebinds a module-level name.

```python
def make_counter():
    count = 0

    def next_value():
        nonlocal count
        count += 1
        return count

    return next_value
```

Prefer returning state or using objects when many functions mutate shared globals. Closures are excellent for small encapsulated state, but hidden mutation in deeply nested scopes can become harder to test and reason about.
