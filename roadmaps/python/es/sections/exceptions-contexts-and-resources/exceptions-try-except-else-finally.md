# Exceptions y Bloques `try`

Las exceptions suben por la call stack hasta un handler. `except` maneja fallos seleccionados, `else` corre si el try tuvo éxito y `finally` siempre corre al salir. El traceback es esencial.

```python
try:
    value = int(text)
except ValueError as exc:
    report(exc)
else:
    use(value)
finally:
    cleanup()
```

Captura solo fallos de los que puedas recuperarte/traducir. Evita `except Exception: pass`. Usa `raise ... from ...` para conservar la causa.
