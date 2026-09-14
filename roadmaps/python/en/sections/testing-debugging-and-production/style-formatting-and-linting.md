# Style, Formatting, and Linting

Python has PEP 8 conventions, while modern projects often use automated formatters, linters, import sorters, static type checkers, and security tools. A consistent toolchain reduces style churn and catches defects before code review.

```python
# Common project tools may include:
# ruff check .
# ruff format .
# python -m pytest
# pyright / mypy
```

Keep configuration in project files and CI so local editors and automation agree. Treat suppressions as small documented exceptions rather than disabling useful checks across the entire codebase.
