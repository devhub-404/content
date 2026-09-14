# Leer Historial con `log` y `show`

`git log` recorre historial reachable y puede filtrar, formatear, dibujar el grafo y limitar el recorrido. `git show` muestra un objeto, normalmente un commit con metadata y patch.

```bash
git log --oneline --graph --decorate --all
git show --stat HEAD
git log -- path/to/file
```

El historial es un grafo, así que filtros de path, author, date, ancestry y grep cambian lo que aparece. Construye el log según la pregunta en vez de memorizar un formato enorme.
