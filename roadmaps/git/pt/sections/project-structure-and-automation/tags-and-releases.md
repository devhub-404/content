# Tags, Releases e Signing

Tags dão nomes estáveis a objetos selecionados, normalmente commits de release. Annotated tags são objetos Git com metadata/message e podem ser assinadas; lightweight tags são refs simples.

```bash
git tag -a v1.0.0 -m "Release 1.0.0"
git push origin v1.0.0
git tag -v v1.0.0
```

Faça push de tags deliberadamente porque push comum de branch não publica necessariamente todas. Signing prova relação com uma key apenas dentro do trust model que o projeto realmente verifica.
