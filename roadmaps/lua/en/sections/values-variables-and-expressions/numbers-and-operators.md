# Numbers and Operators

Lua has integer and floating-point numeric subtypes under the `number` type in a standard build. Arithmetic operators include ordinary addition, subtraction, multiplication, division, floor division, modulo, exponentiation, and bitwise operators for integers.

```lua
local integer = 7
local float = 7.5

print(integer + 2)
print(float / 2)
print(7 // 2)
print(2 ^ 8)
print(0xff)
```

The exact integer and float representations are configuration details of a Lua build, although the standard distribution uses common machine representations. Be explicit about floor division, conversion, and range assumptions when code crosses files, network protocols, C APIs, or other systems with fixed numeric formats.
