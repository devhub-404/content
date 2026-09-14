# `math`, `os` y Basic Library

La basic library contiene helpers como `assert`, `error`, `type`, conversion, loading, metatable operations y protected calls. `math` ofrece funciones numéricas/pseudo-random y `os` recursos seleccionados de process, clock, date, locale, environment y filesystem.

```lua
math.randomseed(1234)

print(math.sqrt(81))
print(math.random(1, 6))
print(os.date("%Y-%m-%d"))

local value = tonumber("42")
assert(value == 42)
```

Estas libraries son capabilities, especialmente en un runtime embedded/sandboxed. El host puede no abrirlas todas. El random normal no es automáticamente criptográfico y las funciones de OS no deben exponerse a scripts no confiables sin una decisión explícita de seguridad.
