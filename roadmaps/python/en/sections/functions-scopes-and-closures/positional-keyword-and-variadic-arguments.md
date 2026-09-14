# Positional, Keyword, and Variadic Arguments

Python can require positional-only parameters with `/`, keyword-only parameters with `*`, collect extra positional values in `*args`, and extra keyword values in `**kwargs`. These tools make calling conventions part of the API.

```python
def request(url, /, method="GET", *, timeout=5, **headers):
    ...

request("/users", timeout=2, Accept="application/json")
```

Use keyword-only parameters for optional settings where call-site names improve readability and positional-only parameters where the parameter name should not become a compatibility promise. Avoid functions that accept arbitrary `**kwargs` without documenting supported keys.
