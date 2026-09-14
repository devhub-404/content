# Chunks and the Standalone Interpreter

Lua executes source as chunks. A file is a chunk, but a chunk can also come from a string or from code loaded by a host application. The standalone `lua` program loads and runs chunks and exposes command-line arguments through the conventional `arg` table.

```lua
-- hello.lua
local name = arg[1] or "world"
print("Hello, " .. name)
```

A chunk is compiled before execution and behaves much like the body of a variadic function. This matters when you later use `load`, modules, custom environments, or the C API: Lua is not limited to “running files”; code is data that a host can load under controlled conditions.
