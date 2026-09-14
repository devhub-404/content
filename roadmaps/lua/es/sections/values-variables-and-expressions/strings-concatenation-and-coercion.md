# Strings, Concatenación y Conversión

Las strings de Lua son secuencias inmutables de bytes y pueden contener bytes arbitrarios, incluido cero. `..` concatena y `#` devuelve la longitud en bytes. Las strings entre comillas soportan escapes y los long brackets son útiles para texto multilínea.

```lua
local language = "Lua"
local version = 5.5

local label = language .. " " .. tostring(version)
print(label)
print(#label)
```

Usa `tostring` y `tonumber` cuando la conversión forme parte de la intención en vez de depender de coerciones implícitas históricas. El encoding es responsabilidad de la aplicación; la library `utf8` ayuda con code points UTF-8, mientras las operaciones básicas siguen orientadas a bytes.
