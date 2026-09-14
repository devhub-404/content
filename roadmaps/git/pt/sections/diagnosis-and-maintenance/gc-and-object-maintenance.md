# Garbage Collection e Manutenção do Repositório

Git armazena objetos loose e packed e periodicamente faz manutenção para otimizar storage/reachability. Comandos comuns já podem acionar manutenção automática, então `git gc` manual não é rotina após cada workflow.

```bash
git count-objects -vH
git gc
git maintenance run
```

Repositórios grandes podem se beneficiar de maintenance agendada, commit-graph e repack. Meça o comportamento e use mecanismos do Git em vez de deletar `.git/objects` manualmente.
