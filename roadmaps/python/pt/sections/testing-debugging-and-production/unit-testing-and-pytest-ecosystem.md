# Unit Testing e Ecossistema de Testes

Standard library inclui `unittest`, enquanto pytest é third-party amplamente usado com fixtures, assertions, parametrization e plugins.

```python
import unittest

class CalculatorTest(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)
```

Teste comportamento e invariantes, não replique implementação. Integration tests são necessários para banco, files, HTTP, packaging e framework wiring. Bons testes verificam comportamento observável e deixam a causa da falha clara quando uma regression aparece.
