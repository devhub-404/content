# Números y Operadores

Lua tiene subtipos numéricos integer y floating-point dentro de `number` en un build estándar. Los operadores incluyen suma, resta, multiplicación, división, floor division, módulo, exponenciación y operadores bitwise para integers.

```lua
local integer = 7
local float = 7.5

print(integer + 2)
print(float / 2)
print(7 // 2)
print(2 ^ 8)
print(0xff)
```

Las representaciones exactas de integer/float son detalles configurables del build, aunque la distribución estándar usa formatos comunes de máquina. Sé explícito sobre floor division, conversión y rangos cuando los datos cruzan archivos, protocolos, C APIs u otros sistemas con formatos fijos.
