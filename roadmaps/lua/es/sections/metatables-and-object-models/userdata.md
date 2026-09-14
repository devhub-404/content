# Userdata y Objetos del Host

Userdata permite que C u otro host exponga objetos foreign opacos manteniendo la representación real fuera de las tables Lua. Las metatables aportan methods, operators, cleanup hooks y comportamiento parecido a valores nativos.

```lua
-- From Lua, host userdata can look like this:
local file = host.open_file("report.txt")
file:write("hello")
file:close()
```

El host debe definir ownership y lifetime: si Lua posee el recurso, lo toma prestado, puede cerrarlo explícitamente y qué ocurre después de close. Un binding seguro impide que el script conserve un pointer a almacenamiento nativo ya destruido.
