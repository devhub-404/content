# Variables To-be-closed y Cleanup de Recursos

Una variable local marcada `<close>` se finaliza cuando el control sale del scope, incluso por error, según las reglas to-be-closed. El valor debe soportar `__close`, y los file handles estándar participan en este modelo.

```lua
local file <close> = assert(io.open("report.txt", "w"))
file:write("hello
")
-- file is closed when the scope ends
```

Úsalo para cleanup determinista de files, locks, transactions o recursos del host que no deben esperar al GC. Mantén adquisición y scope próximos. El garbage collection es un respaldo para memoria, no un sustituto de liberar a tiempo recursos externos.
