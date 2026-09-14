# Indentation, Statements, and Expressions

Indentation is syntactic structure in Python: blocks follow a colon and are defined by consistent indentation. Expressions produce values, while statements perform language actions such as assignment, import, return, raise, loops, and definitions.

```python
value = 10

if value > 0:
    label = "positive"
else:
    label = "non-positive"

result = value * 2
```

Use a formatter such as Black or another project-standard formatter to eliminate style drift, but still understand indentation and line-continuation rules because syntax errors and scopes are defined by the language, not the formatter.
