# Guardar Trabajo Temporal con Stash

Stash registra estado seleccionado del working tree/index sucios para permitir un checkout limpio sin crear un commit normal en el historial del proyecto. Las stash entries son objetos Git referenciados por una pila especial.

```bash
git stash push -m "WIP parser"
git stash list
git stash pop
```

Usa stash para cambios temporales de contexto, no como task tracker de largo plazo. Commits pequeños en una branch temporal suelen ser mejores cuando el trabajo durará más que una interrupción breve.
