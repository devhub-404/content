# Cherry-pick de Commits Selecionados

Cherry-pick aplica a mudança introduzida por commit existente na branch atual e registra novo commit. Ele copia a mudança, não a identidade do grafo, então source e destination normalmente têm object IDs diferentes.

```bash
git cherry-pick <commit>
git cherry-pick <oldest>^..<newest>
```

Use para transferência seletiva deliberada, como backports ou um fix necessário em outra linha. Não é substituto geral para merge de uma relação inteira, pois cópias repetidas complicam integração posterior.
