# Números e Operadores

Lua possui subtipos numérico integer e floating-point dentro de `number` em um build padrão. Operadores incluem soma, subtração, multiplicação, divisão, floor division, módulo, exponenciação e operadores bitwise para integers.

```lua
local integer = 7
local float = 7.5

print(integer + 2)
print(float / 2)
print(7 // 2)
print(2 ^ 8)
print(0xff)
```

As representações exatas de integer/float são detalhes configuráveis do build, embora a distribuição padrão use formatos comuns de máquina. Seja explícito sobre floor division, conversão e ranges quando dados cruzam arquivos, protocolos, C APIs ou sistemas com formatos fixos.
