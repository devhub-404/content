# Commits e Historial de Parents

Un commit referencia un snapshot y normalmente un parent; los merge commits tienen varios parents. Seguir esos enlaces produce el historial como un grafo dirigido, no como una única secuencia lineal universal.

```bash
git show --stat HEAD
git log --oneline --parents -5
```

Una branch avanza a un nuevo commit cuando haces commit en ella. Los commit IDs cambian cuando cambia el contenido o metadata, por eso rebase y amend crean commits nuevos aunque los archivos finales se parezcan.
