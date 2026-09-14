# Unit Testing y Ecosistema de Tests

La standard library incluye `unittest`, mientras pytest es third-party ampliamente usado con fixtures, assertions, parametrization y plugins.

```python
import unittest

class CalculatorTest(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)
```

Prueba comportamiento e invariantes, no dupliques implementación. Los integration tests son necesarios para base de datos, files, HTTP, packaging y framework wiring.
