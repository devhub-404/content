# Expressões Regulares

Module `re` suporta patterns, groups, substitutions, flags e lookarounds. Raw strings são comuns para evitar double escaping.

```python
import re

match = re.fullmatch(r"user-(\d+)", "user-42")
if match:
    user_id = int(match.group(1))
```

Regex é ótima para padrões lexicais, mas pode ficar ilegível em gramáticas estruturadas. Use string methods em regras simples e parsers dedicados quando grammar/errors importam.
