# Registering Native Functions and Userdata

A host can expose C functions as Lua callables and group them into libraries. Full userdata stores host-controlled memory managed through Lua's lifetime machinery, while light userdata is essentially a raw pointer value with much weaker ownership semantics.

```lua
-- After the host registers a library:
local socket = net.connect("example.com", 443)

socket:send("hello")
socket:close()
```

Prefer full userdata plus metatables for owned native objects. Validate every Lua argument before using it in native code, define close/finalization behavior, and never assume a pointer remains valid simply because Lua still holds a value representing it. Binding code is a trust boundary.
