# Configuración de Remotes

Un remote es un nombre para URLs y configuración de mapeo de refs usada en fetch/push. `origin` es solo un nombre convencional creado por clone; un repositorio puede tener varios remotes para forks, mirrors o destinos separados.

```bash
git remote -v
git remote add upstream <repository-url>
git remote set-url origin <new-url>
```

Nombra los remotes por su función cuando haya varios, como `origin` para tu fork y `upstream` para el proyecto canónico. Inspecciona URLs antes de push en repositorios con destinos parecidos o sensibles.
