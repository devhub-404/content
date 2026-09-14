# Generators and `yield`

A function containing `yield` returns a generator iterator. Its local state is suspended between values and resumes when the consumer asks for the next item, making generators natural for streaming, traversal, and pipelines.

```python
def even_numbers(limit):
    for value in range(0, limit + 1, 2):
        yield value

for value in even_numbers(10):
    print(value)
```

Generator code runs lazily, so exceptions and I/O may occur during iteration rather than when the generator is created. Make sure resources remain valid for the whole iteration, or use a context manager that owns the generator lifecycle.
