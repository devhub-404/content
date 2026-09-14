# Hacer Push de Refs con Seguridad

Push envía objetos ausentes y solicita actualizar refs remotas. Un push normal se rechaza cuando descartaría historial remoto según las reglas, protegiendo trabajo añadido desde tu último estado conocido.

```bash
git push -u origin feature/login
git push origin main
git push --force-with-lease
```

Si la reescritura es intencional, prefiere `--force-with-lease` frente a `--force`: el lease verifica que la ref remota aún coincide con el estado esperado. Las branches protegidas pueden rechazar reescritura de todos modos.
