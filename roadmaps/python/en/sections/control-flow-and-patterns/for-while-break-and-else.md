# `for`, `while`, `break`, and Loop `else`

`for` consumes an iterable rather than using a C-style counter header, while `while` repeats from a condition. `break` exits, `continue` advances, and a loop `else` runs only when the loop finishes without `break`.

```python
for item in items:
    if matches(item):
        found = item
        break
else:
    found = None
```

Loop `else` is useful for search-style logic but can surprise readers unfamiliar with it. Prefer it when it removes a flag cleanly; use an explicit helper function or `next` with a default when that makes the intent clearer.
