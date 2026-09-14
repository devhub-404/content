# Unit Testing and the Testing Ecosystem

The standard library includes `unittest`, while pytest is a widely used third-party test runner with fixtures, concise assertions, parametrization, and plugin support. Both can test ordinary Python code; project conventions often determine which ecosystem is used.

```python
import unittest

class CalculatorTest(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)
```

Test public behavior and invariants rather than duplicating implementation. Integration tests remain necessary for databases, files, HTTP, packaging, subprocesses, and framework wiring that unit doubles cannot prove.
