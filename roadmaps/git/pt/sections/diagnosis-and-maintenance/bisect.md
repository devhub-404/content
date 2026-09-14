# Encontrar Regressão com Bisect

Bisect faz busca binária sobre ancestry entre pontos conhecidos good e bad. Git faz checkout de candidates e usa sua classificação para reduzir o espaço restante.

```bash
git bisect start
git bisect bad
git bisect good <known-good-commit>
# test each checked-out commit, then mark good/bad
git bisect reset
```

Automatize com `git bisect run` quando houver comando de teste confiável. O teste precisa distinguir good, bad e untestable corretamente; do contrário a busca pode apontar para área errada.
