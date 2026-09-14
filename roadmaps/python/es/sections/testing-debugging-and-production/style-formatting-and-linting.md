# Style, Formatting y Linting

Python tiene PEP 8 y proyectos modernos usan formatters, linters, import sorting, static checkers y security tools. Un toolchain consistente reduce style churn y detecta bugs antes del review.

```python
# Common project tools may include:
# ruff check .
# ruff format .
# python -m pytest
# pyright / mypy
```

Mantén la config en proyecto/CI y las suppressions como excepciones documentadas, no desactivación global.
