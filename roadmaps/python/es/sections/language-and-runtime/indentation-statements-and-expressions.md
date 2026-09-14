# Indentación, Statements y Expressions

La indentación forma parte de la sintaxis: los blocks siguen `:` y se definen por indentación consistente. Las expressions producen valores y los statements realizan assignment, import, return, raise, loops y definitions.

```python
value = 10

if value > 0:
    label = "positive"
else:
    label = "non-positive"

result = value * 2
```

Usa un formatter para eliminar drift de estilo, pero entiende indentation/line continuation porque los scopes y syntax errors los define el lenguaje.
