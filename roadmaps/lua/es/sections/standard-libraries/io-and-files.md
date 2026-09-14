# I/O y Archivos

La library `io` expone streams por defecto y file handles. `io.open` devuelve un file object o error, y sus methods leen, escriben, hacen seek, flush y close según el modo.

```lua
local file <close> = assert(io.open("data.txt", "w"))
file:write("alpha
")
file:write("beta
")
file:flush()
```

Comprueba fallos de open/I/O. Usa locals to-be-closed o close explícito para liberar de forma determinista. En Lua embedded, el host puede omitir o reemplazar la I/O library, así que los scripts deben conocer las capabilities reales del runtime.
