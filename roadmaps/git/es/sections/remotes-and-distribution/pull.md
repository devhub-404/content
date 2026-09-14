# Pull y Estrategia de Integración

Pull ejecuta fetch y después integra el upstream seleccionado en la branch actual. La integración puede hacer fast-forward, merge o rebase según options/config, así que “pull” no produce una única forma de historial.

```bash
git pull --ff-only
git pull --rebase
git pull --no-rebase
```

Elige una estrategia explícita de equipo y configúrala. Para máxima visibilidad, haz fetch primero, inspecciona la remote-tracking branch y luego ejecuta merge/rebase por separado.
