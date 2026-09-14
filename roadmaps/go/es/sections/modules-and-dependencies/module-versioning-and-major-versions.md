# Versionado de Modules y Major Versions

Los modules publicados siguen semantic versioning y v2+ normalmente incluye el major suffix en module/import path. Así pueden coexistir majors incompatibles en el mismo build graph.

```go
// v1 import:
import "example.com/lib"

// v2+ import:
import "example.com/lib/v2"
```

No modifiques una tag publicada. Publica otra versión y conserva backward compatibility dentro de una major cuando sea posible. Package paths, identifiers exportados, interfaces y comportamiento forman parte de la compatibilidad.
