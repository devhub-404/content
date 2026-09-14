# Comprehensions

List, set, and dictionary comprehensions express mapping/filtering in compact syntax and have their own local iteration scope. Generator expressions use similar syntax but produce values lazily instead of constructing a full collection.

```python
squares = [x * x for x in values if x > 0]
lookup = {user.id: user for user in users}
unique = {name.casefold() for name in names}
```

Use comprehensions when the transformation remains readable in one expression. Nested loops, several conditions, side effects, or complex error handling are often clearer as ordinary loops or helper functions.
