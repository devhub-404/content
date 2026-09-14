# Comprehensions

Las list/set/dict comprehensions expresan mapping/filtering concisos y tienen scope propio. Las generator expressions usan sintaxis similar, pero producen valores lazy.

```python
squares = [x * x for x in values if x > 0]
lookup = {user.id: user for user in users}
unique = {name.casefold() for name in names}
```

Usa comprehension cuando la transformación quepa de forma legible en una expresión. Nesting, side effects o errores complejos son mejores en loops/helpers.
