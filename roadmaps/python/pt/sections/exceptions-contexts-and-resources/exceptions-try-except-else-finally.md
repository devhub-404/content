# Exceptions e Blocos `try`

Exceptions sobem a call stack até handler. `except` trata falhas selecionadas, `else` roda se try teve sucesso e `finally` sempre roda na saída. Traceback é essencial.

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

Capture apenas falhas que consegue recuperar/traduzir. Evite `except Exception: pass`. Use `raise ... from ...` para preservar cause.
