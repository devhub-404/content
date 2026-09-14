# Registrando Functions Nativas y Userdata

Un host puede exponer C functions como callables Lua y agruparlas en libraries. Full userdata almacena memoria controlada por el host dentro del lifetime de Lua, mientras light userdata es básicamente un raw pointer con semántica de ownership mucho más débil.

```lua
-- After the host registers a library:
local socket = net.connect("example.com", 443)

socket:send("hello")
socket:close()
```

Prefiere full userdata con metatables para objetos nativos owning. Valida argumentos, define close/finalization y nunca supongas que un pointer sigue válido solo porque Lua conserva un valor que lo representa. El binding code es un trust boundary.
