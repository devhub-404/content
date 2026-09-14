# Variáveis To-be-closed e Cleanup de Recursos

Uma variável local marcada `<close>` é finalizada quando o controle sai do scope, inclusive por error, conforme as regras to-be-closed. O valor precisa suportar `__close`, e file handles padrão participam desse modelo.

```lua
local file <close> = assert(io.open("report.txt", "w"))
file:write("hello
")
-- file is closed when the scope ends
```

Use para cleanup determinístico de files, locks, transactions ou recursos host que não devem esperar GC. Mantenha aquisição e scope próximos. Garbage collection é fallback para memória, não substituto de liberação oportuna de recursos externos.
