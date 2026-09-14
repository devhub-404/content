# I/O e Arquivos

A library `io` expõe streams default e file handles. `io.open` retorna file object ou erro, e methods leem, escrevem, seek, flush e close conforme o mode.

```lua
local file <close> = assert(io.open("data.txt", "w"))
file:write("alpha
")
file:write("beta
")
file:flush()
```

Cheque falhas de open/I/O. Use locals to-be-closed ou close explícito para liberação determinística. Em Lua embedded, o host pode remover/substituir a I/O library, então scripts precisam conhecer capabilities reais do runtime.
