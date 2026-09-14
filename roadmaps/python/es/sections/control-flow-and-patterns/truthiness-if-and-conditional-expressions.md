# Truthiness, `if` y Conditional Expressions

Las condiciones usan truth-value testing: `False`, `None`, cero y containers vacíos son false. Los custom objects pueden definir truth mediante `__bool__`/`__len__`. La conditional expression elige entre dos valores.

```python
label = "ready" if ready else "waiting"

if items:
    print("has items")
elif fallback is not None:
    print(fallback)
```

Usa truthiness cuando empty/zero/false realmente signifiquen ausencia. Usa `is None` cuando esos valores sean válidos y distintos de missing.
