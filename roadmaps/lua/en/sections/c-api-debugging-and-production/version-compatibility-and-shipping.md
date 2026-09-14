# Version Compatibility and Shipping Lua

Lua releases within one minor line are designed to remain compatible, but different language versions can change APIs, bytecode, and details of the C ABI. Precompiled chunks from one version should not be treated as portable across different versions.

```lua
local major, minor = _VERSION:match("Lua (%d+)%.(%d+)")

print("Lua version:", major, minor)
```

A product embedding Lua should document the exact supported language line and rebuild native modules when the ABI requires it. Prefer shipping source chunks unless bytecode distribution is a deliberate, version-coupled choice. Test scripts against the same libraries and host capabilities they will receive in production.
