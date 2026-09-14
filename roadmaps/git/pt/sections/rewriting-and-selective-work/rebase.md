# Fazer Rebase de uma Branch

Rebase pega commits exclusivos de uma linha e reaplica mudanças equivalentes sobre nova base, criando novos commits. Os arquivos finais podem coincidir com um merge enquanto o grafo de ancestry fica diferente.

```bash
git switch feature/login
git rebase main
```

Faça rebase livremente em trabalho local não publicado quando ajuda integração. Reescrever commits usados por outros exige coordenação porque object IDs e descendants deixam de coincidir.
