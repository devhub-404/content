# Tags, Releases y Signing

Las tags dan nombres estables a objetos seleccionados, normalmente commits de release. Las annotated tags son objetos Git con metadata/message y pueden firmarse; las lightweight tags son refs simples.

```bash
git tag -a v1.0.0 -m "Release 1.0.0"
git push origin v1.0.0
git tag -v v1.0.0
```

Haz push de tags deliberadamente porque el push normal de branch no publica necesariamente todas. Signing demuestra relación con una key solo dentro del trust model que el proyecto realmente verifica.
