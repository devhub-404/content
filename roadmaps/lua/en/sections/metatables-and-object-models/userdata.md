# Userdata and Host Objects

Userdata lets C or another host expose opaque foreign objects to Lua while keeping their real representation outside ordinary Lua tables. Metatables give userdata methods, operators, cleanup hooks, and other behavior that makes the foreign value feel native to scripts.

```lua
-- From Lua, host userdata can look like this:
local file = host.open_file("report.txt")
file:write("hello")
file:close()
```

The host must define ownership and lifetime carefully: whether Lua owns the resource, borrows it, can close it explicitly, and what happens after close. A safe binding prevents Lua code from retaining a pointer to native storage that has already been destroyed.
