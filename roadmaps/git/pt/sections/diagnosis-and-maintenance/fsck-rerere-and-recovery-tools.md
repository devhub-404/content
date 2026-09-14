# Checks de Integridade e Resolução Repetida de Conflitos

`git fsck` verifica conectividade/validade dos objetos e pode revelar dangling/unreachable objects úteis em recovery. `rerere` registra como um formato de conflito foi resolvido e pode reutilizar essa resolução se reaparecer.

```bash
git fsck --full
git config rerere.enabled true
git rerere status
```

São ferramentas de diagnóstico/workflow, não substitutos de backup ou branch policy. Antes de remover objetos unreachable ou confiar em resolução reutilizada, inspecione o que Git encontrou e rode testes.
