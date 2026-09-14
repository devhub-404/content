# Indentação, Statements e Expressions

Indentação faz parte da syntax: blocks seguem `:` e são definidos por indentation consistente. Expressions produzem valores e statements fazem assignment, import, return, raise, loops e definitions.

```python
value = 10

if value > 0:
    label = "positive"
else:
    label = "non-positive"

result = value * 2
```

Use formatter para eliminar drift de style, mas entenda indentation/line continuation porque scopes e syntax errors são definidos pela linguagem.
