# Functions, Parameters, and Return Values

Functions are runtime objects created by `def`. Parameters can have defaults, and a function returns `None` when execution reaches the end without an explicit result. Defaults are evaluated once when the function definition executes, not on every call.

```python
def connect(host: str, port: int = 443) -> str:
    return f"{host}:{port}"

address = connect("example.com")
```

Do not use a mutable object such as `[]` or `{}` as a default when each call should receive fresh state. Use `None` as a sentinel and create the mutable value inside the function instead.
