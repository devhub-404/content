# Pull e Estratégia de Integração

Pull executa fetch e depois integra upstream selecionado na branch atual. A integração pode fast-forward, merge ou rebase conforme options/config, então “pull” não produz um único formato de histórico.

```bash
git pull --ff-only
git pull --rebase
git pull --no-rebase
```

Escolha estratégia explícita de equipe e configure-a. Para máxima visibilidade, faça fetch primeiro, inspecione remote-tracking branch e então execute merge/rebase separadamente.
