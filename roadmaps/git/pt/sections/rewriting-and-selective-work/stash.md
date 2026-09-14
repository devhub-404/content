# Guardar Trabalho Temporário com Stash

Stash registra estado selecionado da working tree/index sujos para permitir checkout limpo sem criar commit comum no histórico do projeto. Stash entries são objetos Git referenciados por uma pilha especial.

```bash
git stash push -m "WIP parser"
git stash list
git stash pop
```

Use stash para mudanças temporárias de contexto, não como task tracker de longo prazo. Commits pequenos numa branch temporária costumam ser melhores quando o trabalho vai durar mais que uma interrupção curta.
