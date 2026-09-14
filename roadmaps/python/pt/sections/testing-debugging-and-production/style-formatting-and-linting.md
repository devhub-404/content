# Style, Formatting e Linting

Python possui PEP 8 e projetos modernos usam formatters, linters, import sorting, static checkers e security tools. Toolchain consistente reduz style churn e encontra bugs antes do review.

```python
# Common project tools may include:
# ruff check .
# ruff format .
# python -m pytest
# pyright / mypy
```

Mantenha config no projeto/CI e suppressions como exceções documentadas, não desabilitação global.
