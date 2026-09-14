# Checks de Integridad y Resolución Repetida de Conflictos

`git fsck` verifica conectividad/validez de los objetos y puede mostrar dangling/unreachable objects útiles en recovery. `rerere` registra cómo se resolvió una forma de conflicto y puede reutilizar esa resolución si reaparece.

```bash
git fsck --full
git config rerere.enabled true
git rerere status
```

Son herramientas de diagnóstico/workflow, no sustitutos de backups o branch policy. Antes de eliminar objetos unreachable o confiar en una resolución reutilizada, inspecciona lo que Git encontró y ejecuta tests.
