# Archivos y Paths

El package `os` expone files, environment y funciones del sistema, mientras `path/filepath` manipula filesystem paths con separadores nativos. `path` sirve para rutas slash-based como URLs, no para el filesystem local en general.

```go
data, err := os.ReadFile("config.json")
if err != nil {
    return err
}

path := filepath.Join("data", "report.txt")
fmt.Println(path, len(data))
```

`os.ReadFile` es excelente para archivos bounded; streaming mediante `os.File` es mejor para datos grandes. Comprueba errores de open/read/write/sync/close cuando importe la durabilidad. El filesystem puede cambiar por acciones externas.
