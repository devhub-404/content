# Commits e Histórico de Parents

Um commit referencia um snapshot e normalmente um parent; merge commits possuem múltiplos parents. Seguir esses links produz o histórico como um grafo dirigido, não como uma sequência linear universal.

```bash
git show --stat HEAD
git log --oneline --parents -5
```

Uma branch avança para um novo commit quando você commita nela. Commit IDs mudam quando conteúdo ou metadata do commit mudam, por isso rebase e amend criam novos commits mesmo que os arquivos finais pareçam iguais.
