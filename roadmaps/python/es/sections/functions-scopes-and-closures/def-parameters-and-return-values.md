# Functions, Parámetros y Retornos

Las functions son runtime objects creados por `def`. Los parameters pueden tener defaults y la función retorna `None` si llega al final. Los defaults se evalúan una vez cuando se ejecuta la definition.

```python
def connect(host: str, port: int = 443) -> str:
    return f"{host}:{port}"

address = connect("example.com")
```

No uses `[]`/`{}` mutable como default cuando cada call necesite estado nuevo. Usa `None` y crea el objeto dentro.
