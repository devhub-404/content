# Obtener Historial Remoto con Fetch

Fetch contacta un remote, descarga objetos ausentes y actualiza remote-tracking refs configuradas sin integrar commits en la branch actual. Esta separación permite inspeccionar historial recibido antes de decidir cómo mover branches locales.

```bash
git fetch origin
git fetch --all --prune
```

`--prune` elimina remote-tracking refs locales de branches remotas eliminadas. Fetch suele ser la primera operación de red más segura cuando quieres información sin cambiar historial de la branch local.
