# `load`, `loadfile` y Chunks Dinámicos

`load` compila un chunk desde texto o una reader function y devuelve una función ejecutable cuando la compilación tiene éxito. `loadfile` hace lo mismo desde un archivo. Un fallo de compilación se devuelve como resultado sin ejecutar nada automáticamente.

```lua
local fn, err = load("return 20 + 22")

if not fn then
    error(err)
end

print(fn())
```

La carga dinámica sirve para configuración, plugins, código generado y embedding, pero cargar texto no confiable como código concede las capacidades disponibles en su environment. Prefiere formatos de datos cuando solo necesites datos y restringe el environment cuando la configuración ejecutable sea realmente necesaria.
