# Buscar Histórico Remoto com Fetch

Fetch contata remote, baixa objetos ausentes e atualiza remote-tracking refs configuradas sem integrar commits na branch atual. Essa separação permite inspecionar histórico recebido antes de decidir como branches locais devem mover.

```bash
git fetch origin
git fetch --all --prune
```

`--prune` remove remote-tracking refs locais de branches remotas removidas. Fetch costuma ser a primeira operação de rede mais segura quando você quer informação sem mudar histórico da branch local.
