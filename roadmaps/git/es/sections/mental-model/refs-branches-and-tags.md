# Refs, Branches y Tags

Una ref es un nombre legible que apunta a un object ID u otra ref. Las branches locales viven en `refs/heads`, las tags en `refs/tags` y `HEAD` normalmente apunta simbólicamente a la branch actual.

```bash
git branch --show-current
git show-ref --heads --tags
```

Las branches son refs móviles: hacer commit avanza la branch actual. Las tags suelen ser nombres estables para releases o puntos importantes. Por eso crear una branch es barato: crea un nombre, no una copia del proyecto.
