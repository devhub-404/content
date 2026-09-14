# Limpar Arquivos Untracked com Segurança

`git clean` remove arquivos untracked e, com options, diretórios ou ignored files. Esses arquivos podem nunca ter sido armazenados no Git, então a remoção pode ser muito menos recuperável que resetar conteúdo tracked.

```bash
git clean -n
git clean -nd
git clean -f
git clean -fd
```

Faça preview com `-n` antes de forçar e saiba se build artifacts, bancos locais, env files ou assets são ignored ou apenas untracked. Clean é cleanup de filesystem, não operação de histórico.
