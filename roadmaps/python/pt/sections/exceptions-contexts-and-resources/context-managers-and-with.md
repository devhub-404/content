# Context Managers e `with`

Context manager define entry/exit behavior via protocol ou `contextlib`, e `with` garante exit mesmo com exception.

```python
with open(path, "r", encoding="utf-8") as file:
    text = file.read()
```

Use para files, locks, transactions, temporary state, tracing e lifetimes scoped. Comunica ownership/cleanup melhor que open/close separados. Esse padrão deixa aquisição e cleanup no mesmo fluxo e reduz caminhos em que um recurso pode permanecer aberto.
