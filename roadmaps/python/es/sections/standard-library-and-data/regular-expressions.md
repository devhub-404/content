# Expresiones Regulares

El módulo `re` soporta patterns, groups, substitutions, flags y lookarounds. Las raw strings son comunes para evitar double escaping.

```python
import re

match = re.fullmatch(r"user-(\d+)", "user-42")
if match:
    user_id = int(match.group(1))
```

Regex es excelente para patrones léxicos, pero puede volverse ilegible con gramáticas estructuradas. Usa string methods para reglas simples y parsers dedicados cuando importen grammar/errors.
