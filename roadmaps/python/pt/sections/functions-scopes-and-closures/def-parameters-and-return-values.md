# Funções, Parâmetros e Retornos

Functions são runtime objects criados por `def`. Parameters podem ter defaults e a função retorna `None` se chega ao fim. Defaults são avaliados uma vez quando a definition executa.

```python
def connect(host: str, port: int = 443) -> str:
    return f"{host}:{port}"

address = connect("example.com")
```

Não use `[]`/`{}` mutável como default quando cada call precisa estado novo. Use `None` e crie o objeto dentro.
