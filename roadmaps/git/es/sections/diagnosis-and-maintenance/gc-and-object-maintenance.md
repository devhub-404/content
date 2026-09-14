# Garbage Collection y Mantenimiento del Repositorio

Git almacena objetos loose y packed y periódicamente hace mantenimiento para optimizar storage/reachability. Los comandos comunes pueden activar mantenimiento automático, así que `git gc` manual no es una rutina tras cada workflow.

```bash
git count-objects -vH
git gc
git maintenance run
```

Repositorios grandes pueden beneficiarse de maintenance programado, commit-graph y repack. Mide el comportamiento y usa mecanismos de Git en vez de borrar `.git/objects` manualmente.
