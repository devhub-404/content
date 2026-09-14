# Argumentos Positional, Keyword e Variadic

Python pode exigir positional-only com `/`, keyword-only com `*`, coletar extras em `*args`/`**kwargs`. Esses recursos fazem calling convention parte da API.

```python
def request(url, /, method="GET", *, timeout=5, **headers):
    ...

request("/users", timeout=2, Accept="application/json")
```

Use keyword-only em options e positional-only quando o nome do parameter não deve virar contrato. Evite `**kwargs` arbitrário sem documentar keys.
