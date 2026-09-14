# Configuración y Ayuda

La configuración Git puede existir a nivel de sistema, usuario, repositorio y, en setups modernos, worktree. La identidad afecta nuevos commits; aliases, editor, merge behavior, signing y defaults también son configurables.

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --list --show-origin
git help commit
```

Usa `--show-origin` cuando un valor te sorprenda porque varios archivos pueden contribuir. Prefiere configuración documentada frente a aliases de shell que oculten comportamiento importante, especialmente en equipos.
