# Exceptions and `try` Blocks

Exceptions propagate up the call stack until handled. `except` handles selected failures, `else` runs only when the try body succeeds, and `finally` runs during exit regardless of success. Raising an exception preserves a traceback that is crucial for diagnosis.

```python
try:
    value = int(text)
except ValueError as exc:
    report(exc)
else:
    use(value)
finally:
    cleanup()
```

Catch the narrow failures you can actually recover from or translate. Avoid `except Exception: pass`, which hides defects. When adding context, use exception chaining with `raise ... from ...` so the original cause remains available.
