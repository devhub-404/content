# Compatibilidad de Versiones y Distribución

Las releases dentro de la misma minor line están diseñadas para compatibilidad, pero versiones distintas pueden cambiar APIs, bytecode y detalles de la C ABI. Los chunks precompiled no deben tratarse como portables entre versiones.

```lua
local major, minor = _VERSION:match("Lua (%d+)%.(%d+)")

print("Lua version:", major, minor)
```

Un producto embedded debe documentar la language line soportada y recompilar native modules cuando la ABI lo requiera. Prefiere source chunks salvo una decisión deliberada por bytecode ligado a versión. Prueba scripts con las mismas libraries/capabilities de producción.
