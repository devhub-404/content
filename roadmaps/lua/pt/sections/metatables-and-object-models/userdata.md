# Userdata e Objetos do Host

Userdata permite que C ou outro host exponha objetos foreign opacos mantendo a representação real fora de tables Lua. Metatables fornecem methods, operators, cleanup hooks e comportamento semelhante a valores nativos.

```lua
-- From Lua, host userdata can look like this:
local file = host.open_file("report.txt")
file:write("hello")
file:close()
```

O host precisa definir ownership e lifetime: se Lua possui o recurso, faz borrow, pode fechá-lo explicitamente e o que acontece após close. Binding seguro impede script de manter pointer para storage nativo já destruído.
