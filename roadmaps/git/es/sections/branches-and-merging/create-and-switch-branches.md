# Crear y Cambiar Branches

Crear una branch crea una ref móvil en un commit. `git switch` cambia la branch apuntada por `HEAD` y actualiza working tree/index al snapshot correspondiente, siempre que los cambios locales puedan preservarse con seguridad.

```bash
git switch -c feature/login
git switch main
git branch -m feature/auth
```

Los branch names describen líneas de trabajo, no copias de directorios. Mantén cambios committeados o protegidos antes de cambiar cuando se solapen con contenido de la branch destino.
