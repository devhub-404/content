# Comprehensions

List/set/dict comprehensions expressam mapping/filtering concisos e têm scope próprio. Generator expressions usam syntax parecida, mas produzem valores lazy.

```python
squares = [x * x for x in values if x > 0]
lookup = {user.id: user for user in users}
unique = {name.casefold() for name in names}
```

Use comprehension quando a transformação cabe de forma legível em uma expression. Nesting, side effects ou errors complexos ficam melhores em loops/helpers.
